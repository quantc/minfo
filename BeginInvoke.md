# delegate.BeginInvoke not supported in .NET Core

Based on the article https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/

### .NET Framework

```c#
Action<string> SomeAction;
SomeAction.BeginInvoke("param", null, null)
```

### .NET Core

```c#
Action<string> SomeAction;
Task.Factory.StartNew(() => SomeAction("param"));
```
