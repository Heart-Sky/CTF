### 2016 2 29
# MISC
### MISC 驾驶技术科目三
`科目三开始路考了啊，小伙子们快上车！ 车票在0x02.jpg`

刚开始没仔细看题目，对着0x02.zip解压（解压完就把它删了= =）出来的图片弄了好久，就是不行。后来再看题目，是0x02.jpg。丢进虚拟机里strings就找到了一个神秘代码（起初还不知道），是百度网盘链接。下载到这个
!(01.png)[01.png]
双图，最先尝试了各种姿势，最后还是用winhex解决的
!(02.png)[02.png]
然后把不同处扣出来
!(03.png)[03.png]
base64字符串，去解密
又得到一个神秘代码，下载后打开，是一个txt文件，里面有flag，又有一个神秘代码
### MISC 驾驶技术科目四
`开五档上高速，教练带你秋名山。`

上面的代码下载后是这个
!(04.png)[04.png]
有提示，暴力 所以下了个软件穷举压缩包密码，大概几十分钟跑出来的，拿到flag
# WEB
### WEB从0开始之xss challenge0.5
    Try to prompt(1)
    
    function charge(input) {
        var stripTagsRE = /script/gi;
        input = input.replace(stripTagsRE, '');

    return '<article>' + input + '</article>';
    }
刚开始连xss是啥都不知道，谷歌了各种资料，算是有了初步印象
只过滤了script，这个好绕过
`<img src=1 onerror=prompt(1)>`
### WEB从0开始之xss challenge1
    Try to prompt(1)
    
    function charge(input) {
        input = input.replace(/[=(]/g, '');
        return input;
    }
过滤了 = 和 （ ，用script和svg
`<svg><script>prompt&#40;1)</script>`
简单说就是svg里面的元素如果有html实体编码，会先进行解码，所以 `&#40;`会被转换为`（`
# PENTEST
### lightless&aklis的渗透教室-3
!(05.png)[05.png]
不是管理员， 第一反应修改了cookie为`user=admin`(貌似毫无理由= =)
后来f12看了下，在响应头中发现端倪
!(06.png)[06.png]
果然，按里面说的改了后就出flag了
!(07.png)[07.png]
貌似好有趣的样子，继续学！

### 总结：这周难度感觉已经上升许多了，体会到了linux的作用，也遭遇到了从未听说过的题目类型，比如xss，需要学的知识还很多，不过还是挺好玩的。Keep learning!
