In this file we show some asychronize code.
声明的时候需要用到 async 表明是一部方法， 需要用到 Task 
````
Task<int> task =  CountCharactersAsync(1, "http://....")

private async Task<int> CountCharactersAsync(int id, string link)
{
    WebClient wb = new WebClient();
    Console.WriteLine("Starting call {0} : {1}", id, sw.Elapsed.TotalMilliseconds);
    string result = await wb.DownloadStringTaskAsync(new Uri(link));
    Console.WriteLine("CALL {0} completed:  {1, 4} ms", id, sw.Elapsed.TotalMilliseconds);
    return result.Length;
}
````
在这个例子中是有返回值的。 需要返回一个int类型的数据
声明异步方法需要有
