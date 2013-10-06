octopress-weibo
==============================

Display sina weibo show on the awesome blog system Octopress 

## Octopress Aside Plugin For Weibo

A plugin of [Octopress](http://octopress.org/) used for display your recent sina weibo.  
Preview http://www.orcame.com/

### Installation

Get the plugin
```bash
git clone git@github.com:orcame/octopress-weibo.git
cd octopress-weibo
cp weibo.html /root_of_your_blog/source/_includes/asides/
```
Of cause you can copy it to your .theme/your_theme/source/_include/asides folder if you like.

Config your  ```_config.yml``` file.

+ add `asides/weibo.html` to your default_asides array. 

+ navigate to http://app.weibo.com/tool?topnav=1&wvr=5 to get some necessary values.

After this step, you may got the following code snippet.
```html
<iframe width="100%" height="550" class="share_self"  frameborder="0" scrolling="no" src="http://widget.weibo.com/weiboshow/index.php?language=&width=0&height=550&fansRow=2&ptype=1&speed=0&skin=1&isTitle=1&noborder=1&isWeibo=1&isFans=1&uid=3835412420&verifier=61ac6817&dpc=1"></iframe>
```

+ add the following configurations to the end of your ```_config.yml```.

```yaml
# Display sina weibo show
weibo_uid: 3835412420 #required, check the 'uid' value from the code snippet you just got from page http://app.weibo.com/tool?topnav=1&wvr=5 or you can use my uid, I dont mind. :)
weibo_verifier: 61ac6817 #required, check the 'verifier' value from the code snippet. 
weibo_language: zh_cn #optinal, the display language, available value is 'zh_cn' and 'zh_tw',default is 'zh_cn'.
weibo_height: 350 #the px height of the aside.
weibo_fans_row: 0 #the lines used to display your fans, available value is 0-7, 0 means display no fans.
weibo_show_title: false	#display title or not.
weibo_show_weibo: true #show your recent weibo or not.
weibo_scroll_speed: 0 #the speed of auto scroll the aside content. 0 means you shoud scroll it manually.

```

Deploy (if you want)
```
rake generate
rake deploy
```  

**Notice:** This plugin is worked fine on my theme(based on bootstrap), maybe you need adjust some class value or other code on your own theme.
