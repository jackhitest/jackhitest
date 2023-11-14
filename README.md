- 👋 Hi, I’m @jackhitest
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
jackhitest/jackhitest is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


# 源文件路径
$InputFile = "$env:USERPROFILE\Desktop\desip.txt"

# 输出文件路径
$OutputFile = "$env:USERPROFILE\Desktop\tracert.txt"

if (-not (Test-Path -Path $InputFile)) {
    Write-Host "无法找到输入文件 $InputFile"
    exit 1
}

Write-Host "正在执行 tracert 命令..."

# 清空或创建输出文件
Set-Content -Path $OutputFile -Value ""

$Domains = Get-Content $InputFile

for ($i = 0; $i -lt $Domains.Length; $i++) {
    $Domain = $Domains[$i]
    Write-Host "Tracert 结果 for $Domain"
    Add-Content -Path $OutputFile -Value "Tracert 结果 for $Domain"
    tracert -d -w 50 -h 7 $Domain | ForEach-Object {
        Add-Content -Path $OutputFile -Value ("    " + $_)
    }
    Add-Content -Path $OutputFile -Value ""

    # 如果是最后一个域名，停止所有动作
    if ($i -eq ($Domains.Length - 1)) {
        Write-Host "所有tracert命令已完成，请查看 $OutputFile"
        break
    }
}
 
