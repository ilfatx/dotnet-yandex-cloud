Example run ASP.NET Core Web API applications as Yandex Cloud Function.

Install nuget packet Amazon.Lambda.Yandex.0.0.1.nupkg to local repository: nuget add ...

Publish :
To local folder Publish, parameters:
 - linux-x64
 - net6.0
 - Self-contained
 - Trim unused code

 Delete all System.*.dll and *.so except System.Diagnostics.*.dll System.IO.*.dll System.Text.*.dll
 Pack to .zip and load to Yandex Cloud Function to net6

Entry point: WebApplication.YandexFunction
