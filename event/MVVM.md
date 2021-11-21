This document notes down the event and data binding. 
One case about the MVVM and how it works. We focsus on the View and View-Model and how to de-couple the UI design and the service code.
To build the connection between View and View Model, data binding is implemented by **PropertyChanged** event.

## MVVM
Model-View-ViewModel
首先解释 **INotifyPropertyChanged**， 他是一个接口， 用于向客户端发出某一属性值已经更改的通知。
