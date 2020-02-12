var placetext={placeTextContainers:[],placeTextFields:[],placeTextField:function(what,how){how=how||{};if(what.txt&&what.container)placetext.placeText(what.container,what.txt,how.changeFontSize,how.minFontSize,how.showFunction,how.html)},placeText:function(container,txt,changeFontSize,minFontSize,showFunction,html){var n=0;if(ie8){placetext.show(txt,container);return}
if(placetext.placeTextContainers.indexOf(container)==-1){placetext.placeTextContainers.push(container)}
if(placetext.placeTextFields.indexOf(txt)==-1){placetext.placeTextFields.push(txt);n=placetext.placeTextFields.length-1}
else{n=placetext.placeTextFields.indexOf(txt)}
clearTimeout(container.timeout);if((container.height()+1.5<txt.height()||container.width()+1.5<txt.width())&&!container.finished){if(!showFunction){showFunction=placetext.show;txt.css('opacity','0')}
if(changeFontSize){var s=((txt.css('font-size').replace('px',''))-1);minFontSize=minFontSize||9;if(s<minFontSize){if(html){finish();return}
container.timeout=setTimeout(function(){placetext.placeText(container,txt,!1,minFontSize,showFunction)},4)}
else{var lh=Number(txt.css('line-height').replace('px',''));lh=lh*(s/(s+1));txt.css('font-size',s+'px');txt.css('line-height',lh+'px');container.timeout=setTimeout(function(){placetext.placeText(container,txt,!0,minFontSize,showFunction,html)},4)}}
else{if(!txt.t)txt.t=txt.text();txt.t=txt.t.substring(0,txt.t.length-6)+"...";txt.text(txt.t);container.timeout=setTimeout(function(){placetext.placeText(container,txt,changeFontSize,minFontSize,showFunction)},4);container.finished=txt.t.length<5?!0:!1}}
else{finish()}
function finish(){txt.t=undefined;placetext.placeTextFields.splice(n,1);placetext.placeTextContainers.splice(n,1);if(showFunction)showFunction(txt,container)}},stopPlacingText:function(container){var n=placetext.placeTextContainers.indexOf(container);clearTimeout(container.timeout);placetext.placeTextContainers.splice(n,1);placetext.placeTextFields.splice(n,1)},working:function(){return placetext.placeTextContainers.length>0},show:function(txt,con){txt.css('opacity','1')}}
var tools=tools||{};$.extend(!0,tools,placetext)