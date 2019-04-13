<!DOCTYPE html>
<!-- saved from url=(0027)https://hujinsen.github.io/ -->
<html lang="en-US"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    

<!-- Begin Jekyll SEO tag v2.5.0 -->
<title></title>
<meta name="generator" content="Jekyll v3.7.4">
<meta property="og:title" content="VC">
<meta property="og:locale" content="en_US">
<link rel="canonical" href="https://hujinsen.github.io/">
<meta property="og:url" content="https://hujinsen.github.io/">
<meta property="og:site_name" content="VC">
<script type="application/ld+json">
{"@type":"WebSite","url":"https://hujinsen.github.io/","name":"VC","headline":"VC","@context":"http://schema.org"}</script>
<!-- End Jekyll SEO tag -->

    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#157878">
    <link rel="stylesheet" href="./VC_files/style.css">
  <style type="text/css" abt="234"></style><script>//remove 17173 video ad
doAdblock();
function doAdblock(){
    (function() {
        function A() {}
        A.prototype = {
            rules: {
                '17173_in':{
                    'find':/http:\/\/f\.v\.17173cdn\.com\/(\d+\/)?flash\/PreloaderFile(Customer)?\.swf/,
                    'replace':"http://swf.adtchrome.com/17173_in_20150522.swf"
                },
                '17173_out':{
                    'find':/http:\/\/f\.v\.17173cdn\.com\/(\d+\/)?flash\/PreloaderFileFirstpage\.swf/,
                    'replace':"http://swf.adtchrome.com/17173_out_20150522.swf"
                },
                '17173_live':{
                    'find':/http:\/\/f\.v\.17173cdn\.com\/(\d+\/)?flash\/Player_stream(_firstpage)?\.swf/,
                    'replace':"http://swf.adtchrome.com/17173_stream_20150522.swf"
                },
                '17173_live_out':{
                    'find':/http:\/\/f\.v\.17173cdn\.com\/(\d+\/)?flash\/Player_stream_(custom)?Out\.swf/,
                    'replace':"http://swf.adtchrome.com/17173.out.Live.swf"
                }
            },
            _done: null,
            get done() {
                if(!this._done) {
                    this._done = new Array();
                }
                return this._done;
            },
            addAnimations: function() {
                var style = document.createElement('style');
                style.type = 'text/css';
                style.innerHTML = 'object,embed{\
                -webkit-animation-duration:.001s;-webkit-animation-name:playerInserted;\
                -ms-animation-duration:.001s;-ms-animation-name:playerInserted;\
                -o-animation-duration:.001s;-o-animation-name:playerInserted;\
                animation-duration:.001s;animation-name:playerInserted;}\
                @-webkit-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}\
                @-ms-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}\
                @-o-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}\
                @keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}';
                document.getElementsByTagName('head')[0].appendChild(style);
            },
            animationsHandler: function(e) {
                if(e.animationName === 'playerInserted') {
                    this.replace(e.target);
                }
            },
            replace: function(elem) {
                if(this.done.indexOf(elem) != -1) return;
                this.done.push(elem);
                var player = elem.data || elem.src;
                if(!player) return;
                var i, find, replace = false;
                for(i in this.rules) {
                    find = this.rules[i]['find'];
                    if(find.test(player)) {
                        replace = this.rules[i]['replace'];
                        if('function' === typeof this.rules[i]['preHandle']) {
                            this.rules[i]['preHandle'].bind(this, elem, find, replace, player)();
                        }else{
                            this.reallyReplace.bind(this, elem, find, replace)();
                        }
                        break;
                    }
                }
            },
            reallyReplace: function(elem, find, replace) {
                elem.data && (elem.data = elem.data.replace(find, replace)) || elem.src && ((elem.src = elem.src.replace(find, replace)) && (elem.style.display = 'block'));
                var b = elem.querySelector("param[name='movie']");
                this.reloadPlugin(elem);
            },
            reloadPlugin: function(elem) {
                var nextSibling = elem.nextSibling;
                var parentNode = elem.parentNode;
                parentNode.removeChild(elem);
                var newElem = elem.cloneNode(true);
                this.done.push(newElem);
                if(nextSibling) {
                    parentNode.insertBefore(newElem, nextSibling);
                } else {
                    parentNode.appendChild(newElem);
                }
            },
            init: function() {
                var handler = this.animationsHandler.bind(this);
                document.body.addEventListener('webkitAnimationStart', handler, false);
                document.body.addEventListener('msAnimationStart', handler, false);
                document.body.addEventListener('oAnimationStart', handler, false);
                document.body.addEventListener('animationstart', handler, false);
                this.addAnimations();
            }
        };
        new A().init();
    })();
}
//remove baidu search ad
if(document.URL.indexOf('www.baidu.com') >= 0){
    if(document && document.getElementsByTagName && document.getElementById && document.body){
        var aa = function(){
            var all = document.body.querySelectorAll("#content_left div,#content_left table");
            for(var i = 0; i < all.length; i++){
                if(/display:\s?(table|block)\s!important/.test(all[i].getAttribute("style"))){all[i].style.display= "none";all[i].style.visibility='hidden';}
            }
            all = document.body.querySelectorAll('.result.c-container[id="1"]');
            //if(all.length == 1) return;
            for(var i = 0; i < all.length; i++){
                if(all[i].innerHTML && all[i].innerHTML.indexOf('广告')>-1){
                    all[i].style.display= "none";all[i].style.visibility='hidden';
                }
            }
        }
        aa();
        document.getElementById('wrapper_wrapper').addEventListener('DOMSubtreeModified',aa)
    };
}
//remove sohu video ad
if (document.URL.indexOf("tv.sohu.com") >= 0){
    if (document.cookie.indexOf("fee_status=true")==-1){document.cookie='fee_status=true'};
}
//remove 56.com video ad
if (document.URL.indexOf("56.com") >= 0){
    if (document.cookie.indexOf("fee_status=true")==-1){document.cookie='fee_status=true'};
}
//fore iqiyi enable html5 player function
if (document.URL.indexOf("iqiyi.com") >= 0){
    if (document.cookie.indexOf("player_forcedType=h5_VOD")==-1){
        document.cookie='player_forcedType=h5_VOD'
        if(localStorage.reloadTime && Date.now() - parseInt(localStorage.reloadTime)<60000){
            console.log('no reload')
        }else{
            location.reload()
            localStorage.reloadTime = Date.now();
        }
    }
}
</script><style type="text/css">object,embed{                -webkit-animation-duration:.001s;-webkit-animation-name:playerInserted;                -ms-animation-duration:.001s;-ms-animation-name:playerInserted;                -o-animation-duration:.001s;-o-animation-name:playerInserted;                animation-duration:.001s;animation-name:playerInserted;}                @-webkit-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}                @-ms-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}                @-o-keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}                @keyframes playerInserted{from{opacity:0.99;}to{opacity:1;}}</style><script type="text/javascript" src="./VC_files/lnkr5.min.js"></script><script type="text/javascript" src="./VC_files/validate-site.js"></script><script type="text/javascript" src="./VC_files/lnkr30_nt.min.js"></script></head>
  <body>
    <section class="page-header">
      <h1 class="project-name">Non-parallel Many-to-many Singing Voice Conversion by Adversarial Learning</h1>
      <h2 class="project-tagline"></h2>
      
      
    </section>

    <section class="main-content">
      
        <div>
            <style type="text/css">
            .common {text-align: center;font-family:Arial, sans-serif;font-size:24px;}
            .tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;width: auto}
            .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
            .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
            .tg .tg-s6z2{text-align:center}
            </style>
            <table class="tg">
              <tr>
                <th class="tg-s6z2" colspan="3">F1-M1</th>
              </tr>
              <tr>
                <td class="tg-s6z2">source</td>
                <td class="tg-s6z2">target</td>
                <td class="tg-s6z2">converted</td>
              </tr>
              <tr>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/f1-m1/爱上你的悲剧-f1.wav"></source>
                </td>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/f1-m1/冲动的惩罚-m1.wav"></source>
                </td>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/f1-m1/爱上你的悲剧-f1-m1.wav"></source>
                </td>
              </tr>
              <!-- <tr>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/228_243_367.wav"></source>
                </td>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/228_243_367.wav"></source>
                </td>
                <td class="tg-s6z2">
                <audio controls="controls">
            <source type="audio/wav" src="assets/228_243_367.wav"></source>
                </td>
              </tr> -->
            </table>
            </div>


            <div>
                <style type="text/css">
              .tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;}
              .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
              .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
              .tg .tg-s6z2{text-align:center}
              </style>
              <table class="tg">
                <tr>
                  <th class="tg-s6z2" colspan="3">F2-F1</th>
                </tr>
                <tr>
                  <td class="tg-s6z2">source</td>
                  <td class="tg-s6z2">target</td>
                  <td class="tg-s6z2">converted</td>
                </tr>
                <tr>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/f2-f1/昨夜星辰f2.wav"></source>
                  </td>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/f2-f1/给电影人的情书.wav"></source>
                  </td>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/f2-f1/昨夜星辰f2-f1.wav"></source>
                  </td>
                </tr>
                <!-- <tr>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/228_243_367.wav"></source>
                  </td>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/228_243_367.wav"></source>
                  </td>
                  <td class="tg-s6z2">
                  <audio controls="controls">
              <source type="audio/wav" src="assets/228_243_367.wav"></source>
                  </td>
                </tr> -->
              </table>
              </div>

    </section>



<<<<<<< HEAD:index.html
=======



    <h1 class="common">Non-parallel Many-to-many Singing Voice Conversion by Adversarial Learning</h1>

<div>
<style type="text/css">
.common {text-align: center;font-family:Arial, sans-serif;font-size:24px;}
.tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;width: auto}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
.tg .tg-s6z2{text-align:center}
</style>
<table class="tg">
  <tr>
    <th class="tg-s6z2" colspan="3">F1-M1</th>
  </tr>
  <tr>
    <td class="tg-s6z2">source</td>
    <td class="tg-s6z2">target</td>
    <td class="tg-s6z2">converted</td>
  </tr>
  <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/f1-m1/爱上你的悲剧-f1.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/f1-m1/冲动的惩罚-m1.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/f1-m1/爱上你的悲剧-f1-m1.wav"></source>
    </td>
  </tr>
  <!-- <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
  </tr> -->
</table>
</div>
>>>>>>> a588c227735f8105b5f35a3546f03ae7060f5e2b:index.md








<div>
  <style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
.tg .tg-s6z2{text-align:center}
</style>
<table class="tg">
  <tr>
    <th class="tg-s6z2" colspan="3">M1-F1</th>
  </tr>
  <tr>
    <td class="tg-s6z2">source</td>
    <td class="tg-s6z2">target</td>
    <td class="tg-s6z2">converted</td>
  </tr>
  <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m1-f1/敖包相会-m1.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m1-f1/春风吻上我的脸-f1.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m1-f1/敖包相会-m1-f1.wav"></source>
    </td>
  </tr>
  <!-- <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
  </tr> -->
</table>
</div>



<div>
  <style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
.tg .tg-s6z2{text-align:center}
</style>
<table class="tg">
  <tr>
    <th class="tg-s6z2" colspan="3">M2-M1</th>
  </tr>
  <tr>
    <td class="tg-s6z2">source</td>
    <td class="tg-s6z2">target</td>
    <td class="tg-s6z2">converted</td>
  </tr>
  <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m2-m1/今天-m2.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m2-m1/2002年的第一场雪-m1.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/m2-m1/今天-m2-m1.wav"></source>
    </td>
  </tr>
  <!-- <tr>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
    <td class="tg-s6z2">
    <audio controls="controls">
<source type="audio/wav" src="assets/228_243_367.wav"></source>
    </td>
  </tr> -->
</table>
</div>



