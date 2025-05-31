---

layout: post
title: Vim Language
date: 2020-05-13 22:00 +0630
author: "Naing Naing Htun"
header-style: text
tags: [Guide, Vim]

---

Vim မှာ texts တွေကို copy, paste, delete လုပ်ချင်တာမျိုးမှာဘယ်လိုသုံးမလဲ။ ပုံမှန်အတိုင်း Insert mode ထဲဝင် `Backspace` နဲ့တစ်လုံးချင်းဖျက်။ အဲ့လိုလည်းရသလို Normal mode ထဲမှာပဲနေပြီး ပြင်လို့ရပါသေးတယ်။ copy, paste, delete မှ မဟုတ်ပါဘူး တစ်ခြား operation တွေလဲရှိပါသေးတယ်။ ဒီမှတော့ copy ကို yank အဖြစ်ပဲသုံးပါတယ်။

Normal mode မှာ operation/action တစ်ခုလုပ်ချင်ရင် operator, (text object or motion), count (optional) အဲ့ key တွေပေါင်းရပါတယ်။

*Example*

-	`daw`	-	delete a word

ပုံမှန် English လိုပါပဲ။ လက်ရှိ cursor postion ကနေပြီးတော့ word တစ်လုံးကို delete လုပ်မယ်လို့ပြောလိုက်တာပါ။ delete 3 words ဆိုရင် `d3w` ပေါ့။ ဒီနေရာမှာ `d` က operator `3` or `a` က count/text object နဲ့ `w` က motion ပါ။ တစ်ခြားရှိသေးတဲ့ operator တွေ text object နဲ့ motion တွေကိုအောက်မှာ ဖော်ပြပါမယ်။

>**action	=	[operator] [count] [text object / motion]**

>**action	=	[count] [operator] [text object / motion]**

ဒီနှစ်ခုက သုံးတာတူတူပါပဲ။ ဘယ်လိုကွာသွားလဲဆိုတော့

`d2w` က delete 2 words ဖြစ်ပြီး
`2dw` က delete word operation ကို 2 ကြိမ်လုပ်မယ်လို့ပြောတာပါ။ result ကတော့တူတူပါပဲ။

## Operators

-	**`c`	-	change**
-	**`d`	-	delete**
-	**`y`	-	yank into register/copy into register**
-	**`p`	-	paste**
-	`g~`	-	swap case
-	`gU`	-	make uppercase
-	`gu`	-	make lowercase
-	`<`	-	shift left
-	`>`	-	shift right
-	`=`	-	indent

`c` မှာတော့ တခြား operator တွေနဲ့မတူတာက insert mode ထဲကိုတစ်ခါထဲရောက်သွားတာဖြစ်ပါတယ်။ ကျန်တဲ့ operator တွေကတော့ intuitive ဖြစ်မယ်ထင်ပါတယ်။
vim မှာက delete က အပြီးဖျက်တာမျိုးမဟုတ်ဘဲ register ထဲမှာသိမ်းထားပါသေးတယ်။ `daw` လုပ်ပြီး `p` ပြန်လုပ်လိုက်ရင် ပြန်ပေါ်လာပါတယ်။
operator ကို motion နဲ့တွဲမသုံးဘဲ နှစ်ကြိမ်နှိပ်လိုက်ရင် action က line တစ်လိုင်းလုံးပေါ်သက်ရောက်ပါတယ်။

*Example*

-	`dd`	-	delete a line
-	`yy`	-	yank a line
-	`2yy`	-	yank 2 line

## Text Objects

-	**`aw`	-	a word**
-	**`iw`	-	inner word**
-	**`aW`	-	a WORD**
-	**`iW`	-	inner WORD**
-	`ap`	-	a paragraph
-	`ip`	-	inner paragraph

`a` နဲ့ `i` ကို `""` `''` ` `` ` `()` `[]` `<>` `{}` တွေနဲ့လည်းတွဲသုံးလို့ရပါတယ်။ 

`""` `''` ` `` ` ဒီဟာတွေနဲ့ action လုပ်မယ်ဆိုရင် cursor position က သက်ဆိုင်ရာ block တွေပေါ်မှာရှိနေစရာမလိုပါဘူး။

ဒါပေမယ့် `()` `[]` `<>` `{}` ဒီဟာတွေနဲ့ action လုပ်မယ်ဆိုရင် cursor position က သက်ဆိုင်ရာ block တွေပေါ်မှာရှိနေမှရပါမယ်။

`a` `i` `w` `W` တွေကဘယ်လိုကွာလဲဆိုတာအောက်မှာကြည့်ရအောင်ပါ။

*Example*
> "**Y**ou'll never know."

*Note	: Initial cursor position is on the word `Y` but not `"`*

အပေါ်ကစာကြောင်းမှာ
`w` ဆိုရင် `You` ကိုယူပြီး `W` ဆိုရင် `You'll` ကိုယူပြီး operate ပါတယ်။
`i"` ဆိုရင် နောက်က `"` အတွဲရဲ့ အတွင်းထဲက texts ကိုယူပြီး `a"` ဆိုရင် `"` အတွဲနဲ့ သူ့အတွင်းထဲက texts တွေကိုပါယူပြီး operate တာပါ။

-	`daw`	-	"'ll never know."
-	`daW`	-	never know."
-	`di"`	-	""
-	`da"`	-	 {empty string}

## Motion

-	`[count] f/F {char}`	-	to next occurence of {char}
-	`[count] t/T {char}`	-	to before next occurence of {char}
-	`[count] w/W`	-	to the start of next [count] word/WORD
-	`[count] b/B`	-	to the start of previous [count] word/WORD
-	`[count] e/E`	-	to the end of next [count] word/WORD

ဒါတွေအပြင် အရင် post မှာပြောထားတဲ့ motion key တွေဖြစ်တဲ့ `^` `$` `h j k l` တွေလည်းပါပါတယ်။

*Example*

-	`fa`	-	to the first `a` character on the line
-	`3fa`	-	to the third `a` character on the line

ကိုယ် find လုပ်လိုက်တဲ့ character က တစ်လိုင်းထဲမှာ အများကြီးရှိနေရင် `;` နဲ့ cycle လုပ်လို့ရပါတယ်။

`.` command လည်းရှိပါသေးတယ်။ `.` က နောက်ဆုံးလုပ်ခဲ့တဲ့ action ကိုပြန်ခေါ်တာပါ။ ခဏခဏရိုက်စရာမလိုတော့ဘူးပေါ့။
