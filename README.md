長庚大學 大數據分析方法 作業三
================

網站資料爬取
------------

``` r
#這是R Code Chunk
library(rvest)
```

    ## Warning: package 'rvest' was built under R version 3.3.3

    ## Loading required package: xml2

    ## Warning: package 'xml2' was built under R version 3.3.3

``` r
dataframeAll<-""
for(n in 7120:7115){
ptt<-paste0("https://www.ptt.cc/bbs/LoL/index",n,".html")
pttContent<-read_html(ptt)
post_title <- pttContent %>% html_nodes(".title") %>% html_text()
post_pushNum <- pttContent %>% html_nodes(".nrec") %>% html_text()
post_author <- pttContent %>% html_nodes(".author") %>% html_text()
ptt_posts <- data.frame(pushNum=post_pushNum,title = post_title, author=post_author)
dataframeAll<-rbind(dataframeAll,ptt_posts)
}
```

    ## Warning in `[<-.factor`(`*tmp*`, ri, value = ""): invalid factor level, NA
    ## generated

    ## Warning in `[<-.factor`(`*tmp*`, ri, value = ""): invalid factor level, NA
    ## generated

爬蟲結果呈現
------------

``` r
#這是R Code Chunk
knitr::kable(dataframeAll) 
```

| pushNum | title                                            | author       |
|:--------|:-------------------------------------------------|:-------------|
|         | NA                                               | NA           |
|         | Re: \[問題\] 國動的崛起是否意味著lol走偏了       | tigotigo5566 |
| 12      | \[問題\] 潘森是線霸嗎?                           | FrogStar     |
| X2      | \[閒聊\] 探討犽宿的風牆效用                      | Baledu       |
|         | (本文已被刪除) \[LIN6627\]                       | -            |
|         | \[問題\] 不投降跟風氣差 跟張家兄弟有什麼關係?    | godband5566  |
| X1      | \[閒聊\] 打野該積極gank嗎                        | FollowMe6    |
| 1       | Re: \[閒聊\] Apex回答太狂 還是大魚功力不足？     | birdanderson |
| 69      | \[閒聊\] 國棟的鼻地戰術是傳承了中國武術？        | stu88001     |
|         | (本文已被刪除) \[qwertytrew\]                    | -            |
|         | \[閒聊\] 賈克斯打sup為啥不行                     | tigotigo5566 |
| 6       | Re: \[閒聊\] Apex回答太狂 還是大魚功力不足？     | InnGee       |
| 31      | \[問題\] 殞落王者之劍是不是很適合特朗德?         | FrogStar     |
| 18      | \[閒聊\] WS如果要贏到底還缺了甚麼東西?           | orange0319   |
| 17      | \[實況\] 胡瓜太郎 Otofu 台服鑽二Sup遊玩中        | goodjob622   |
| 89      | \[實況\] M17 APEX                                | shan0825     |
| 21      | \[問題\] ARAM也有高低端場分別嗎?                 | osbsd1       |
| 23      | \[實況\] FW NL / 煞氣o狂by衝崩銨                 | ns96729      |
| 9       | \[閒聊\] 解說記得的正宗中文教學                  | diefish5566  |
| 2       | \[問題\] 丁特有考慮練蒙多醫生JG嗎？              | ru04ul4      |
| 8       | \[閒聊\] HKE韓服成績真的深不可測                 | stben        |
| 13      | \[閒聊\] 會看EU&其他區比賽的人 是用什麼心情在看? | jakert123    |
| 58      | \[外絮\] Peanut安慰沒進入季後賽的Gorilla         | aaronshell   |
| 9       | \[閒聊\] 如果實況界沒統神現在會是甚麼風氣?       | KENDO777     |
| 20      | \[影片\]【國動】被戳到爆氣開啟動粉見面會         | sky082       |
|         | Re: \[閒聊\] 如果實況界沒統神現在會是甚麼風氣?   | ardan3355    |
|         | (本文已被刪除) \[asd0952\]                       | -            |
|         | \[揪團\] 金牌彈性-1                              | jun12344     |
| 50      | \[閒聊\] Apex回答太狂 還是大魚功力不足？         | Tiandai      |
| 22      | \[閒聊\] Weekly LCK Mic check                    | s80554       |
|         | (本文已被刪除) \[pttpig\]                        | -            |
| 51      | Re: \[閒聊\] Apex回答太狂 還是大魚功力不足？     | bingtsien    |
|         | (本文已被刪除) \[melon1001\]                     | -            |
| 35      | \[閒聊\] 有沒有專精克雷德的玩家來交流個          | silly7995    |
| 1       | \[揪團\] 找上白金的夥伴                          | trollriven   |
| 2       | \[揪團\] 銅銀小號雙排                            | FJUmars      |
| X1      | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | McHamburger  |
|         | \[實況\] 刺刺的 韓服 金三                        | ym19950822   |
|         | (本文已被刪除) \[hongou\]                        | -            |
|         | \[實況\] 藍色風暴 龍獸 金牌RANK<sub>~</sub>      | pcnetworld   |
| 5       | Re: \[問題\] 國動的崛起是否意味著lol走偏了       | tenshoufly   |
|         | \[閒聊\] 是不是應該拔除某些玩家的投票權          | joshua0606   |
| 6       | \[閒聊\] 同人圖分享-你以為有貓我就會推嗎？       | f222051618   |
| 11      | \[閒聊\] 【統神】深夜真性情—那些年的誤會委屈     | g8320484816  |
| 17      | \[閒聊\] 小熊 Yuniko FB                          | Comebuy      |
| 18      | \[ANSI\] 瓦羅然沒有派對                          | AlzioNever   |
| 46      | \[閒聊\] 大家按Q技能會用小拇指嗎?                | phillp0804   |
| 4       | Re: \[問題\] 國動的崛起是否意味著lol走偏了       | sincossincos |
| 3       | Re: \[閒聊\] 這季MVP該給誰                       | Re12345      |
| 11      | \[閒聊\] 一發死的角色是不是逐漸消失中?           | greattower   |
| 2       | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | kingion      |
|         | (本文已被刪除) \[dant123\]                       | -            |
| 78      | \[發錢\] 國考放榜來猜猜灰鵝喜歡的LCK選手(Done)   | where1993    |
| 37      | \[閒聊\] HKE vs. M17 G2 分析台+國人訪問逐字      | eltar        |
| 15      | Re: \[閒聊\] 大家按Q技能會用小拇指嗎?            | s930406      |
| 2       | Re: \[閒聊\] LMS春季第一隊的上路會是誰？         | willia5566   |
| 9       | Re: \[問題\] 國動的崛起是否意味著lol走偏了       | arrenwu      |
| 3       | Re: \[閒聊\] LMS春季第一隊的上路會是誰？         | kingion      |
| 17      | \[閒聊\] 美板官方粉絲團 FB                       | Comebuy      |
| 30      | \[閒聊\] ROC是不是很悲情？                       | andy82116    |
| 3       | \[電競\] 2017 NA LCS夏季升降賽Day3 NV vs. GCU    | cherrycheese |
| 爆      | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | ice91312     |
| 2       | \[閒聊\] 是不是只有進入遊戲畫面才知道ping值      | supereight   |
| 78      | \[公告\] 樂透退盤處置說明                        | rainnawind   |
| 29      | Re: \[閒聊\] Gear是不是真的過譽了？              | Re12345      |
|         | \[實況\] 獄胤天 清明時節雨紛紛 分分塊來RRR       | asdfg5247    |
| 10      | \[問題\] 國動的崛起是否意味著lol走偏了           | fdfdfdfd51   |
| 2       | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | ArtemXis     |
| 30      | \[閒聊\] 這季MVP該給誰                           | zzsh3533     |
| 59      | \[閒聊\] 恭喜M17 (已發)                          | China666     |
| 23      | \[閒聊\] 四強的各路大家覺得強度比較？            | godshibainu  |
| 31      | (已被rainnawind刪除) <frank123ya>                | -            |
| 2       | \[實況\] HKE KuKu / 口口口口口 跟韓國人定輸贏    | a089069      |
| 54      | \[閒聊\] M17要是5人同時醒著 能給前兩隊衝擊嗎?    | JuicyChen    |
| 15      | (本文已被刪除) \[FrogStar\]                      | -            |
|         | (本文已被刪除) \[AlzioNever\]                    | -            |
| 25      | \[外絮\] Kt Score:會拿出如粉絲所期待的表現       | ubiqui       |
| 3       | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | wade8204     |
| 爆      | \[公告\] 在此向frank123ya公開致歉                | rainnawind   |
| 2       | (已被samhou6刪除) <ArtemXis> D1                  | -            |
| 26      | \[閒聊\] 本周LMS觀賽重點整理                     | InnGee       |
| 7       | \[閒聊\] HKE打不進季後賽之後該如何補強?          | a25270672    |
| 3       | \[閒聊\] 同人圖分享-海潮之音 娜米 Nami           | f222051618   |
| 24      | \[閒聊\] Gear是不是真的過譽了？                  | HomerEDLee   |
| 21      | \[閒聊\] 鐘老闆現在在想什麼?                     | brave0618    |
| 2       | \[電競\] LCL SPRING 2017-SEMIFINAL D2            | vic830710    |
| 15      | \[閒聊\] 最喜歡隊友選什麼角色                    | HAHEinthebar |
| 7       | (已被rainnawind刪除) <jumpballfan>Done           | -            |
| 5       | \[實況\] SKT T1 kkOma                            | narutodante  |
| 1       | \[揪團\] 秀造型NG團~ 關鍵字 -3 9:25              | main9        |
|         | \[實況\] 性感荷官 彈性積分/慎上路                | MRsoso       |
| 52      | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | fkc          |
| 60      | \[電競\] 2017 LCS EU Spring W10D4 Final Day      | frank123ya   |
|         | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | a127         |
| 18      | \[閒聊\] 2017 LMS春季聯賽Highlight Reel 第三集   | Comebuy      |
|         | \[閒聊\] Gemini李星到底在幹嘛? 站著發呆10幾秒    | generalfungi |
| 7       | \[閒聊\] 為啥明明是他路差距卻都怪gear            | SanyaMyBride |
| 8       | \[閒聊\] HKE很愛炒短線?                          | China666     |
| 4       | \[公告\] LoL 樂透取消                            | \[彩券\]     |
|         | Re: \[問題\] 死不投降是不是台服素質如此差的原因? | loki5566     |
| 6       | \[揪團\] 陪我一起打好不好(滿)                    | oneeee       |
| 60      | \[閒聊\] FW Betty FB(三則)                       | c871111116   |
| 6       | \[閒聊\] hke的下路是不是太有信心?                | brave0618    |
| 7       | Re: \[問題\] 玩LOL玩到跟弟弟吵架                 | fdfdfdfd51   |
| 24      | \[閒聊\] M17泰山醒了嗎                           | ss8901234    |
| 35      | \[閒聊\] ZZZ可以當LMS前三上路了吧？？            | jeff95123    |
| 1       | \[電競\] TCL WINTER 2017-PLAYOFF R1D2            | vic830710    |
| 7       | \[問題\] 第二場Gemini在幹嘛                      | DioEraclea   |
|         | \[閒聊\] 還我特哥= =                             | YamCha       |
| 17      | \[問題\] 如果剛剛HKE中路是西門                   | gn01914712   |
| X2      | \[影片\] Faker用西門3V5 penta kill               | powyo        |
| 4       | \[揪團\] 邊緣人連假NG團 第一場粗花               | joesmile     |
| 7       | \[外絮\] VG賽後采訪：打比賽時沒那麼大的心理壓力  | iamwhoim     |
| 29      | \[閒聊\] HKE洞在哪?                              | s24066774    |
| 14      | \[閒聊\] JT要怎麼抵擋手已經熱了的M17             | iamfenixsc   |
| 26      | \[閒聊\] M17的宰制力...我看錯聯賽了？            | LKK549777    |
| 22      | \[閒聊\] HKE少了Toyz這名智商型選手 真的差太多了  | vovzz        |
| 67      | \[實況\] 斗基督機大神/鬼話新聞紅蟻               | d86249       |
| 2       | \[揪團\] 小號積分                                | undefeated04 |
|         | (本文已被刪除) \[vogue38\]                       | -            |
| 21      | \[閒聊\] LMS春季第一隊的上路會是誰？             | bygamantou   |

解釋爬蟲結果
------------

``` r
#這是R Code Chunk
dim(dataframeAll)
```

    ## [1] 121   3

共爬出121篇文章（第一篇為null）。

``` r
#這是R Code Chunk
table(dataframeAll$author)
```

    ## 
    ##            -       Baledu birdanderson  diefish5566    FollowMe6 
    ##           13            1            1            1            1 
    ##     FrogStar  godband5566   goodjob622       InnGee      ns96729 
    ##            2            1            1            2            1 
    ##   orange0319       osbsd1      ru04ul4     shan0825        stben 
    ##            1            1            1            1            1 
    ##     stu88001 tigotigo5566   aaronshell    ardan3355    bingtsien 
    ##            1            2            1            1            1 
    ##      FJUmars    jakert123     jun12344     KENDO777  McHamburger 
    ##            1            1            1            1            1 
    ##   pcnetworld       s80554    silly7995       sky082   tenshoufly 
    ##            1            1            1            1            1 
    ##      Tiandai   trollriven   ym19950822   AlzioNever    andy82116 
    ##            1            1            1            1            1 
    ##      arrenwu cherrycheese      Comebuy        eltar   f222051618 
    ##            1            1            3            1            2 
    ##  g8320484816   greattower   joshua0606      kingion   phillp0804 
    ##            1            1            1            2            1 
    ##      Re12345      s930406 sincossincos    where1993   willia5566 
    ##            2            1            1            1            1 
    ##      a089069     ArtemXis    asdfg5247     China666   fdfdfdfd51 
    ##            1            1            1            2            2 
    ##  godshibainu     ice91312    JuicyChen   rainnawind   supereight 
    ##            1            1            1            2            1 
    ##       ubiqui     wade8204     zzsh3533       [彩券]         a127 
    ##            1            1            1            1            1 
    ##    a25270672    brave0618          fkc   frank123ya generalfungi 
    ##            1            2            1            1            1 
    ## HAHEinthebar   HomerEDLee     loki5566        main9       MRsoso 
    ##            1            1            1            1            1 
    ##  narutodante       oneeee SanyaMyBride    vic830710   bygamantou 
    ##            1            1            1            2            1 
    ##   c871111116       d86249   DioEraclea   gn01914712   iamfenixsc 
    ##            1            1            1            1            1 
    ##     iamwhoim    jeff95123     joesmile    LKK549777        powyo 
    ##            1            1            1            1            1 
    ##    s24066774    ss8901234 undefeated04        vovzz       YamCha 
    ##            1            1            1            1            1

就扒到的內容來看，Comebuy發表的文章數目最多，共有3篇。

其他爬蟲結果: 就爬到的結果來看，LOL版面中的文章基本以
*閒**聊*
為主，像
*實**況*
和
*提**問*
 這類的文章很少，看的人也很少。
