---
title: "WWW 0x17: 再見 weekly"
date: 2020-07-17T00:00:00+08:00
tags:
  - Rust
  - DevOps
  - Kubernetes
---

這裡是 WWW 第貳拾參期，Wow Weihang Weekly 是一個毫無章法的個人週刊，出刊週期極不固定，從一週到五年都有可能。初期內容以軟體工程為主，等財富自由後會有更多雜食篇章。

## Weekly 無限期停刊

很遺憾要在此宣布 Wow Weihang Weekly 將無限期停刊，這一期沒意外會是最後一期，其實很訝異自己可以堅持半年每個禮拜都出三篇文章摘要，但至今週刊已經逐漸脫離初衷。當初想寫週刊主要有兩個原因：咀嚼自己所見並分享，還有當作資料庫供未來查詢。我覺得 WWW 一直有達到分享的功效，但卻僅僅止於「摘要」，而且若當週事務繁忙，就連摘要都看起來像是摘要機器人產生出來的，這種純手工的事情，我覺得不需要人類介入，這是第一個停刊理由。

第二個則是週刊很難供自己日後查詢使用，你只能在週刊標題和標籤上下文章，了不起之後做一個站內全文搜尋，但這樣都太過繁瑣，我希望有一個心智圖或是關係圖的呈現方式將我所學串連起來，並提供給其他人參考我怎麼連結每個概念，但週刊的形式真的力有未逮，放棄這條路可能是個不錯的選擇。

相信我們會再相見的。

## 兩個不錯的 Rust 入門學習資源

最近越來越多人對 Rust 產生興趣，這裡就來推薦除了 [TRPL](https://doc.rust-lang.org/book/) 以外，可以快速上手（~~其實不行~~）的學習資源：

- [Rust 程式設計語言（正體中文版）](https://rust-lang.tw/book-tw/)：其實就是 TRPL 的翻譯版，是 Rust Taiwan 社群近期嘔心理解的作品，有任何問題請到 [GitHub Repo 回應](https://github.com/rust-tw/)或直接寄送[GitHub 站內郵件給我](mailto:weihanglo@users.noreply.github.com)。
- [A half-hour to learn Rust](https://fasterthanli.me/articles/a-half-hour-to-learn-rust)：一個我覺得 blog post 幹話很多的 Rustacean 寫的三十分鐘學習 Rust（結果預計閱讀時間顯示 51 分鐘 😂），範例程式碼超多，很適合熟透其他語言的開發者閱讀，會發現 Rust 語法其實非常現代（當然還有可愛的 [Turbofish](https://turbo.fish/))，在還沒進入 lifetime 前完全可以快速掌握 XD
- [Tour of Rust](https://tourofrust.com)：向 [A Tour of Go](https://tour.golang.org/) 致敬的專案，Rust 版本涵蓋的主題非常全面，static/dynamic dispatch 都講了，其實已經超越入門了。但不得不說 Go 版本讀取速度快不少，而且自己魔改的 Ferris 有夠醜。總歸一句還是很值得作為入門讀物，尤其是有 Playground 很方便。

## [Multitenancy Webinar: Better walls make better tenants](https://www.cncf.io/webinars/multitenancy-webinar-better-walls-make-better-tenants/)

Google 的人來講怎麼做 Kubernetes 的 multi-tenancy，基本上是透過 namespace 切分 tenancy，就可以做到在同一個 cluster 內「共享資源」和「限制資源」。這篇演講完整複習了 namespace resource limit、limit range，到 pod security policy 和 network policy 種種和 multi-tenancy 相關的設定，可為抱佛腳大全。

此外，也提到正在 k8s-sig 的 [hierachical namespace](https://github.com/kubernetes-sigs/multi-tenancy/tree/master/incubator/hnc)，可以讓 namespace 將各種 policy 傳遞下去，非常適合複雜團隊使用。

節錄我覺得全文最重要的地方：

> **What does “multitenancy in Kubernetes” mean?**
>
> Provide _isolation_ and _fair resource sharing_ between multiple users and their workloads within a _single cluster_.
