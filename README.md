解决了lucksheet不显示工具栏问题。
具体解决位置：
resize.js 136行增加：let containerLeft = $('#' + Store.container).offset().left；
141 行增加：if(toobarWidths[index] - containerLeft < gridW - 90){

if(toobarWidths == undefined){
       return;
   }
   let containerLeft = $('#' + Store.container).offset().left
   // 找到应该隐藏的起始元素位置
   for (let index = toobarWidths.length - 1; index >= 0; index--) {

       // #luckysheet-icon-morebtn button width plus right is 83px
       if(toobarWidths[index] - containerLeft < gridW - 90){
           moreButtonIndex = index;
           if(moreButtonIndex < toobarWidths.length - 1){

               ismore = true;
           }
           break;
       }
   }


Copyright (c) 2020-present, mengshukeji
