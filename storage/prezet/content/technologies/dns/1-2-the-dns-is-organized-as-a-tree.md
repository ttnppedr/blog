---
title: DNS 的組成像樹一樣
date: 2024-09-17
slug: the-dns-is-organized-as-a-tree
category: Course
excerpt: DNS 從最基礎開始 - DNS 的組成像樹一樣
---

聯合資料庫是由很多小的資料庫組成的，這些小資料庫合併起來變成一個大的資料庫。如果把 DNS 視為聯合資料庫的話，首先而來的問題是，它是怎麼拆分成小的資料庫的呢？

例如： **google.com**。它會被分成兩個部分，一個是 **google**，另一個是 **com**。這些小的字串可以被組成成一個大的字串， **google.com**。

最上層是 DNS root 根節點，往下一個子節點是 **com** ，再往下一個子節點是 **google** 。

所有的域名都是用這樣的方式所組成的。 甚至 [ai](http://ai/) 也是一個有效的域名。

舉個例子， **.tw** 底下有很多子網域，分為屬性型網域及泛用型網域，屬性型網域有其使用方式(參考 [TWINC 域名類別](https://www.twnic.tw/dnservice_catag.php))， **.gov.tw** 是屬性型網域可以被用來表示台灣政府的域名，**chiayi.gov.tw** 被用來表示台灣底下的嘉義市政府。

這樣的查詢是一個遞迴的過程，從 DNS root 到 **.tw** 到 **.gov.tw** 到 **chiayi.gov.tw** ，它他可能無限制的一直下去，但是實務上會有一些限制。

現在我們來談談網域表示法，在這棵樹中的每個節點稱為標籤， **chiayi**、**gov** 和 **tw** 都是標籤，根標籤是一個空字串(**""**)，標籤由有點(**.**)分並。所以 **chyayi** **[.]** **gov** **[.]** **tw** **[.]**，最後一個點通常會被省略。但是根據網頁伺服器的設定方式，兩個都是可以被接受的，例昌 **google.com** 也可以是 **google.com.**。

### References

- [The DNS course for developers](https://www.nslookup.io/dns-course/)
