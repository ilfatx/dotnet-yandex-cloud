# dotnet-yandex-cloud
Example run ASP.NET Core Web API applications as Yandex Cloud Function.

Установить nuget пакет Amazon.Lambda.Yandex.0.0.1.nupkg в локальный репозитории через nuget add ...

Публиковать через Publish :
Публиковать через Publish в локальную папку с параметрами:
 - linux-x64
 - net6.0
 - Автономный
 - Обрезать

 Удалить все System.*.dll и *.so кроме System.Diagnostics.*.dll System.IO.*.dll System.Text.*.dll
 Запаковать в .zip архив и загрузить в Yandex Cloud Function в net6

 Точка входа: WebApplication.YandexFunction
