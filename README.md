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

API Gateway:

openapi: 3.0.0
info:
  title: Sample Web API
  version: 1.0.0
servers:
- url: https://....apigw.yandexcloud.net
paths:
  /hello:
    get:
      x-yc-apigateway-integration:
        type: dummy
        content:
          '*': Hello, World!
        http_code: 200
        http_headers:
          Content-Type: text/plain
  /test:
    get:
      summary: Get Test
      operationId: gettest10
      tags:
        - example
      x-yc-apigateway-integration:
        type: cloud_functions
        function_id: ...
        payload_format_version: "1.0"
        tag: "$latest"
      responses:
        '200':
          description: Ok
  /api/{param+}:
    x-yc-apigateway-any-method:
      summary: Get Controllers
      parameters:
        - name: param
          in: path
          required: true
          schema:
            type: string
      operationId: getcontrollers
      tags:
        - example
      x-yc-apigateway-integration:
        type: cloud_functions
        function_id: ...
        payload_format_version: "1.0"
        tag: "$latest"
      responses:
        '200':
          description: Ok
