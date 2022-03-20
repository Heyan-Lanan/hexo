---
title: 我的书签
date:
  '[object Object]': null
comments: false
---
<script src="https://cdn.jsdelivr.net/npm/jquery@latest/dist/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/jinghu-moon/jinghu-moon.github.io@main/js/bookmarks.js"></script>
<style>
@font-face{font-family:'LXGW WenKai';src:url('./font/LXGWWenKai-Regular.woff2') format('woff2'),url('./font/LXGWWenKai-Regular.woff') format('woff');font-weight:normal;font-style:normal;font-display:swap}
.links-content{margin-top:1rem}
.link-navigation::after{content:" ";display:block;clear:both}
.card{position:relative;width:25%;padding:0;border-radius:10px;transition-duration:.3s;margin-bottom:1.5rem;margin-left:16px;display:block;float:left;box-shadow:0 0 6px 1px rgb(0 0 0 / 10%);background:transparent;overflow:hidden;border:none !important;padding:10px !important;padding-bottom:0 !important}
.card:hover:before,.card:focus:before,.card:active:before{-webkit-transform:translateX(0);transform:translateX(0)}
.card:before{content:"";position:absolute;z-index:-1;top:0;left:0;right:0;bottom:0;background-image:linear-gradient(to top,#e4f0f5 0%,#e4f0f5 100%);-webkit-transform:translateY(209px);transform:translateY(209px);-webkit-transition-property:transform;transition-property:transform;-webkit-transition-duration:0.25s;transition-duration:all 0.25s;-webkit-transition-timing-function:ease-out;transition-timing-function:ease-out}
.card:hover,.card:hover>.card-header a,.card:hover>.card-content a{transform:translateY(-10px)}
@media(max-width:567px){.card{margin-left:20px;width:calc((100% - 20px)/2)}
.card:nth-child(2n+1){margin-left:0}
.card:not(:nth-child(2n+1)){margin-left:20px}
}@media(min-width:567px){.card{margin-left:20px;width:calc((100% - 40px)/3)}
.card:nth-child(3n+1){margin-left:0}
.card:not(:nth-child(3n+1)){margin-left:40px}
}@media(min-width:768px){.card{margin-left:16px;width:calc((100% - 60px)/4)}
.card:nth-child(4n+1){margin-left:0}
.card:not(:nth-child(4n+1)){margin-left:20px}
}.card .card-header{display:block;padding:.25rem .5rem;font-weight:bolder;white-space:nowrap;font-family:'微软雅黑';font-size:16px;background-color:transparent;cursor:pointer;border:none}
.card .card-header a{text-decoration:none;border:0;overflow:hidden}
.card .card-header a:hover{color:#222222;text-decoration:none;border:0}
.card .card-content{font-family:'LXGW WenKai';display:block;text-align:left;margin:.5rem .5rem;margin-top:0;font-weight:500;font-size:smaller;color:#9e9e9e;height:44px;word-break:break-all;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.card .card-content a{font-style:normal;color:#222222;font-weight:500;text-decoration:none;border:0;overflow:hidden}
.stars_h2{color:#000}
</style>



<h2 class="stars_h2"></h2>

<div><div class="links-content"><div class="link-navigation mine"></div></div></div>

<div>
    <div class="links-content">
        <div class="link-navigation mine">
            <div class="card" onclick="window.open('https://console.upyun.com/dashboard/')">
                <div class="card-header">
                    <div>又拍云</div>
                </div>
                <div class="card-content">
                    <div>免费提供 CDN 加速和云存储服务</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://console.cloud.tencent.com/')">
                <div class="card-header">
                    <div>腾讯云</div>
                </div>
                <div class="card-content">
                    <div>域名、服务器购买，DNS 解析，网站备案。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://vercel.com/dashboard')">
                <div class="card-header">
                    <div>vercel</div>
                </div>
                <div class="card-content">
                    <div>CDN 加速，备用。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://github.com/')">
                <div class="card-header">
                    <div>Github</div>
                </div>
                <div class="card-content">
                    <div>全球最大的代码托管平台。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://docsmall.com/image-compress')">
                <div class="card-header">
                    <div>docsmall</div>
                </div>
                <div class="card-content">
                    <div>图片压缩，支持 jpg、png 格式。主用。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('http://color.oulu.me/')">
                <div class="card-header">
                    <div>渐变色</div>
                </div>
                <div class="card-content">
                    <div>180 种渐变色，可复制 CSS 代码，下载渐变色图片。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://imgupscaler.com/')">
                <div class="card-header">
                    <div>Image Upscaler</div>
                </div>
                <div class="card-content">
                    <div>人工智能技术放大图片，肉眼基本看不出区别。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://www.iconfont.cn/')">
                <div class="card-header">
                    <div>阿里巴巴矢量图标库</div>
                </div>
                <div class="card-content">
                    <div>图标非常多，支持 CSS、JS 引用，支持多种格式下载。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://imyshare.com/')">
                <div class="card-header">
                    <div> iMyShare</div>
                </div>
                <div class="card-content">
                    <div>精品实用网络资源导航，我愿称之为全网最强导航。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://www.appinn.com/')">
                <div class="card-header">
                    <div>小众软件</div>
                </div>
                <div class="card-content">
                    <div>分享免费、小巧、实用、有趣、绿色的软件。软件控最爱。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://b3log.org/siyuan/')">
                <div class="card-header">
                    <div>思源笔记</div>
                </div>
                <div class="card-content">
                    <div>一款本地优先的个人知识管理系统，支持完全离线使用，同时也支持端到端加密同步。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://zhutix.com/')">
                <div class="card-header">
                    <div>致美化</div>
                </div>
                <div class="card-content">
                    <div>最专业的桌面美化交流平台，打造属于自己的 windows。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://www.bilibili.com/')">
                <div class="card-header">
                    <div>哔哩哔哩</div>
                </div>
                <div class="card-content">
                    <div>娱乐、学习两不误，我在 B 站上大学。</div>
                </div>
            </div>
            <div class="card" onclick="window.open('https://gfsoso.soik.top/image.html')">
                <div class="card-header">
                    <div>九尾搜搜</div>
                </div>
                <div class="card-content">
                    <div>结果来自谷歌图片，无须科学上网。搜涩图，很准！</div>
                </div>
            </div>
        </div>
    </div>
</div>