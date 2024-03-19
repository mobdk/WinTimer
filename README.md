# WinTimer
Wrapper for Mimikatz with delayed execution

Mimikatz embedded as C# classes, the class Resolver put it all together in memory as byte array.

All the API calls:

VirtualAlloc
CreateEventW
CreateTimerQueue
CreateTimerQueueTimer
WaitForSingleObject
DeleteTimerQueue
CloseHandle

Is resolved from memory, find base address of kernel32.dll and then search for hash ROR13 value and jump to memory address of this functions.

Delays can be effective approach, in this example CreateTimerQueueTimer is used.

Compile: (only csc.exe, VS is not supported)

C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /platform:x64 /target:exe /unsafe WinTimer.cs

