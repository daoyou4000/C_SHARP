This document notes down the event and data binding. 
One case about the MVVM and how it works. We focsus on the View and View-Model and how to de-couple the UI design and the service code.
To build the connection between View and View Model, data binding is implemented by **PropertyChanged** event.

## MVVM
Model-View-ViewModel
### INotifyPropertyChanged
首先解释 **INotifyPropertyChanged**， 他是一个接口， 用于向客户端发出某一属性值已经更改的通知。
````
class NotifyObject : INotifyPropertyChanged
{
    public event PropertyChangedEventHandler PropertyChanged;

    public void RaiseProertyChanged (string propertyName)
    {
        this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

}
````
事件 **PropertyChanged** 是用于 **Binding Data** 数据绑定, 界面上输入界面数据会及时传入到ViewModel, ViewModel 中数据变化也会及时传到界面。
使用的函数就是 void RaiseProertyChanged (string propertyName)；

### ICommand 接口
这个接口用于绑定的 **Button** 命令, 类 **DelegateCommand** 含有两个方法。
- CanExecute 方法判断是否可以执行
- Execute 方法进行执行
````
在实现中会先判断是否可以执行，如果返回false 则不会执行。

class DelegateCommand : ICommand
    {
        public event EventHandler CanExecuteChanged;
        /// <summary>
        /// this is used to make assessment whether the command can execute or not
        /// </summary>
        /// <param name="parameter"></param>
        /// <returns></returns>
        public bool CanExecute(object parameter)
        {
            if(CanExecuteFunc == null)
            {
                return true;
            }
            return CanExecuteFunc(parameter);
        }

        /// <summary>
        ///  if there is no action delegation then return directly
        ///  if not then execute the action delegation
        /// </summary>
        /// <param name="parameter"></param>
        public void Execute(object parameter)
        {
            if (CanExecuteAction == null)
            {
                return;
            }
            CanExecuteAction(parameter);
        }

        public Action<object> CanExecuteAction { set; get; }
        public Func<object, bool> CanExecuteFunc { get; set; }
    }
````
