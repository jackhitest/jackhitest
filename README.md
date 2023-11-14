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



www.tes.com
www.myimaths.com
mathsbox.org.uk
bossmaths.com
mathswatch.co.uk
www.piximaths.co.uk
www.savemyexams.co.uk
www.discoveryeducation.com
www.primaryresources.co.uk
www.thesafeguardingcompany.com
gceguide.com
www.classoos.com
www.twinkl.com.cn
www.pearsonactivelearn.com
pastpapers.papacambridge.com
https://eu.bbcollab.com
www.bing.com


erevison.uk
10ticks.co.uk
www.doublestruck.co.uk
www.drfrostmaths.com
www.physicsandmathstutor.com
revisionworld.com
mrcarter.com
www.educator.co.uk
www.jollyphonice.co.uk
brianmac.co.uk
eric.ed.gov
www.art2day.co.uk
kahoot.com
https://quizlet.com

*playcrey.com
*labarca.cn
*1v1.lol
*krunker.io
*poki.*
*armorgames.com
*crazygames.*
*frvr.*
*blobcraft.duckdns.org
*horse-games.*
*agame.*
*douyin.*
*ixigua.*
*kuaishou.*
*huoshanzhibo.*
*iirose.*
*slope.fun
*.szsyzs.*
*ys.mihoyo.*
*meetyou.*
Startgamer
Yandex
Yohoho
4399 
*bilibili*
*microsoftedge.microsoft.com
*douyin*
*pornhub*
*web.wechat.com*
*roblox*
*chrome.google.com/webstore/category/extensions*
*y8.com*
*iqiyi.com*
*qzone.qq.com*
*xiaohongshu.com*
*v.qq.com*
*youku.com*
*toutiao.com*
*netflix.com*
*web.whatsapp.com*
*wegame.com*
*brightcove.com*
*snapchat.com*
*tumblr.com*
*gamer.qq.com*
*hubsport.com*
*start.qq.com*
*ac.qq.com*
*tecentgames.com*
*pvp.qq.com*
*sj.qq.com*
*gp.qq.com*
*hy.163.com*
*store.steampowerd.com*
*salesforce.com*
*reddit.com*
*im.qq.com*
*uservoice.com*
*live.xbox.com*
*instagram*
*mc.163.*
*minecraft*
*i.qq*
*tv.sohu*
*taming.io*
7k7k.com
totaljerkface.com
*bitlifegame.*
*epicgames.*


 
