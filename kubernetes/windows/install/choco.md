Chocolatey 是什麼?

在過去在 Windows 安裝軟體應用程式時，需要下載安裝檔與使用其軟體安裝流程步驟等各種 GUI 介面，如果需要安裝多個軟體時使用上很繁瑣，Chocolatey 是在 Windows 上的套件管理工具，它結合 Nuget 基礎服務與 powershell 指令，提供快速安裝應用程式與需要工具的服務，主要是將安裝軟體的內容封裝到一個安裝包中，在 Chocolatey 中只需要一條簡單的 command line，就可以完成搜尋、安裝、更新、解安裝等操作，詳細更多說明可以參考 官方文章 What is Chocolatey?。

安裝 Chocolatey
安裝方式很簡單，可以透過下列兩種方式安裝 chocolatey
使用 cmd.exe
在命令提示字元執行以下指令
~~~
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy 
Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" 
&& SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
~~~

使用 Powershell
透過 powershell 安裝前，須先透過 Get-ExecutionPolicy 得知目前系統的指令檔執行限制

~~~
Get-ExecutionPolicy
~~~

如果顯示的是 Restricted，則需要執行下列指令 變更 Windows PowerShell 執行原則的使用者喜好設定
會跳出提示是否要變更執行原則提示，如下圖所示
~~~
Set-ExecutionPolicy AllSigned
or
Set-ExecutionPolicy Bypass -Scope Process
 
執行原則變更
執行原則有助於防範您不信任的指令碼。如果變更執行原則，可能會使您接觸到 about_Execution_Policies 說明主題 (網址為
https:/go.microsoft.com/fwlink/?LinkID=135170) 中所述的安全性風險。您要變更執行原則嗎?
[Y] 是(Y)  [A] 全部皆是(A)  [N] 否(N)  [L] 全部皆否(L)  [S] 暫停(S)  [?] 說明 (預設值為 "N"):
~~~
設定完畢執行原則後，接著輸入下列指令安裝 chocolatey
~~~
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object 
System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
~~~
安装示例
~~~
choco install winrar
~~~