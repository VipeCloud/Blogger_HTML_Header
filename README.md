Blogger_HTML_Header
===================

Here's how to add an html header to a Blogger dynamic view. Add the below before the `</body>` tag. Should work on mobile and desktop view. 

Inspired from:
http://www.frontendlab.net/2013/03/how-to-add-facebook-like-box-plugin-in.html
http://www.atozbuzz.com/2012/07/edit-blogger-mobile-templates.html


```
<b:if cond='data:blog.isMobile'>
<script language='javascript' type='text/javascript'>
$(document).ready(function() {
  var addHTML = function() {
	var iframe_height = 150;
	var header_top = iframe_height + 30;
	var header_bar_height = iframe_height + 60;
	var search_margin_top = iframe_height;
	var main_margin_top = iframe_height + 10;
    $(".header-bar").prepend("<iframe allowTransparency='true' frameborder='0' height='"+iframe_height+"px' scrolling='no' src='//v.vipecloud.com/hello_bar.html' width='100%'/>");
    $(".header-drawer").attr("style","top:"+header_top+"px;");
    $(".header-bar").attr("style","height:"+header_bar_height+"px;");
    $("#search").attr("style","margin-top:"+search_margin_top+"px");
    $("#main").attr("style","margin-top:"+main_margin_top+"px");
  };
  var checkSearchBar = function() {
    if ($("#search").length > 0) {
      addHTML();
    } else {
      setTimeout(checkSearchBar, 100);
    }
  };
  checkSearchBar();
});
</script>
<b:else/>
	<script language='javascript' type='text/javascript'>
$(document).ready(function() {
  var addHTML = function() {
	var iframe_height = 50;
	var header_drawer_margin_top = iframe_height + 65;
	var header_bar_height = iframe_height + 65;
	var search_margin_top = iframe_height + 5;
	var main_margin_top = iframe_height + 5;
	var gadget_dock_top = iframe_height + 125;
    $(".header-bar").prepend("<iframe allowTransparency='true' frameborder='0' height='"+iframe_height+"px' scrolling='no' src='//v.vipecloud.com/hello_bar.html' width='100%'/>");
    $(".header-drawer").attr("style","position:static;margin-top:"+header_drawer_margin_top+"px");
	$(".header-bar").attr("style","height:"+header_bar_height+"px");
	$("#search").attr("style","margin-top:"+search_margin_top+"px");
	$("#main").attr("style","margin-top:"+main_margin_top+"px");
	$("#gadget-dock").attr("style","top:"+gadget_dock_top+"px");
  };
  var checkSearchBar = function() {
    if ($("#search").length > 0) {
      addHTML();
    } else {
      setTimeout(checkSearchBar, 100);
    }
  };
  checkSearchBar();
});
</script>
</b:if>
```
