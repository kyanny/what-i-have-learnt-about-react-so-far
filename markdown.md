class: center, middle

# What I have learnt about React so far...

### 「入門 React」を読んで React について学んだこと

.right[Kensuke Nagae (@kyanny)]

.right[May 20 2015, Shibuya.rb]

---

# I have read this book

.center[![入門 React](http://www.oreilly.co.jp/books/images/picture_large978-4-87311-719-5.jpeg)]

.center[[入門 React](http://www.oreilly.co.jp/books/9784873117195/) / [Developing a React Edge](http://shop.oreilly.com/product/9781939902122.do?sortby=publicationDate)]

---

# I found 2 strengths of React

### React の強みは二つあると思った

1. Simple (primitive) architecture
  * すげー単純なアーキテクチャ
2. Fast and intelligent rendering algorithm
  * すげー賢くて速いレンダリングのアルゴリズムと実装

---

# 1. Simple (primitive) architecture

React application follows this rule:

* Every DOM subtrees are "Component"
* Component has "state"
* "State" will be changed by events
  * timers
  * user interactions
  * asynchronous requests etc.
* Once "state" is changed, every time re-render all components from root of tree
* 「なんかイベント発生して画面が変化するときは画面を丸ごと全部レンダリングしなおそう！」という、雑という意味での単純さ

---

# Example: Todo app made by Backbone and React

Backbone と React で「状態」の扱い方がどう違うかサンプルコードを書いた

* Backbone version
  * http://example.com
  * State is managed by very limited DOM element and its Backbone.View
  * The view instance is not unsure about the state of its DOM element (HTML attributes, jQuery's "data", etc.)
* React version
  * http://example.com
  * State is managed by component itself
  * State is always reflected to the rendered DOM

---

# 2. Fast and intelligent rendering algorithm

### ようやく Virtual DOM の話

The "Virtual DOM": a kind of cache

* "Every time re-render all components from root" is slow
* React knows which component must be rendered again
* Other components are re-used (cache is fast)
* 「DOM は遅い、 React は Virtual DOM だから速い」という説明は、大事な部分を端折りすぎている
* 「毎回全画面イチからレンダリングする仕組みのほうが単純で把握しやすい！」→「...でも実際にやると遅くて使い物にならない」を経て「すげー賢いアルゴリズムでレンダリング処理を高速化したら解決したぜ！」という流れ

---

# The strengths of React

### 改めて React の強みまとめ

1. Simple (primitive) architecture for understanding code execution flow more easy
  * easy to read, easy to trace, easy to debug
  * 単純なアーキテクチャのおかげで処理の流れが追いやすくなる（大規模なアプリケーションで役立つ）
2. Fast and intelligent rendering algorithm for complement "every time re-render all component" strategy
  * no need to abandon beautiful architecture
  * 単純なアーキテクチャだと現実に問題となる「遅さ」を賢いレンダリングアルゴリズムで補う

---

# So, what is the "Flux" architecture?

### で、 Flux ってのは何なの？

* I am still learning, but...
  * Flux aims to extend React's simple (primitive) architecture desgin to not only View layer but also Model layer
  * Flux は React のすげー単純なアーキテクチャを View 層だけでなく Model 層へも広げようという試み

---

# Look back the React Todo app example

* http://example.com
  * localStorage を操作するコードがあちこちのイベントハンドラに散らばっている
  * データの処理（Model 層）の流れを追いづらい
    * せっかく React が View (DOM) →イベント発生→画面のレンダリングまでの処理の流れを一本化してくれたのに...

---

# Point of Flux

* React brings promising architecture design to View layer. Why not do same thing to Model layer?
* React が View 層でやった「どこか変化したら全部書き換えよう（処理の流れを一本化して把握しやすくしよう）」というのと同じことを Model 層でもやればいいじゃん、というのが Flux の狙い

---

# So should I use React and/or Flux?

### で、結局 React と Flux は使うべきなの？

* I recommend to learn React (it's not so hard to learn, fun to use, and insightful)
* If your app is small enough (maybe for fun/hobby), ok to forget Flux
* If your app is large (maybe for production, made by team), Flux is good to consider
* React は見た目 (JSX) ほど難しくないし、面白いので試してみるのをオススメ
* Flux はチーム開発で React 採用を考えてるなら検討・研究してみたほうがよさそう

---

class: center, middle

# Thank you!
