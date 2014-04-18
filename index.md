# JavaScriptでKeyframeAnimationをつくろう

---

## 自己紹介
![](https://avatars2.githubusercontent.com/u/730940?s=200)

宇野 陽太([@cancer6](https://twitter.com/cancer6))

株式会社モバイルファクトリーというところでフロントエンドエンジニアやってます

---

# css animation

---

## css animation

- CSSにkeyframe書いて...
- アニメーション用のclassを作ってプロパティ書いて...
- JSからclassの操作して...
- ...

---

# めんどくさい

---

# どうせJS使うなら全部JSでやってしまおう

---

## css-animations.js

https://github.com/jlongster/css-animations.js

- DOMからCSSにアクセスして色々やってくれる
 - CSSファイルで定義したkeyframeを取ってきたり
 - JavaScriptから動的にkeyframeを生成したり
- オブジェクトでkeyframeのプロパティを渡してあげる

```
var anim1 = CSSAnimations.get('anim1');
var anim2 = CSSAnimations.create('anim2', {
    '0%': { 'background-color': 'red' },
    '100%': { 'background-color': 'blue' }
```

--

## css-animations.js

- アニメーションのプロパティ(animation-name/animation-durationなど)は別途DOMを操作して挿入
- ベンダープレフィックスが必要なプロパティの記述が冗長
 - transform系のプロパティも冗長になりがち

```
var anim = CSSAnimations.create('anim', {
    '0%': {
      opacity: "0.5",
      border-radius: "0"
      "-webkit-border-radius": "0"
      transform: "translate(0, 0) rotate(90deg) scale(1)"
      "-webkit-transform": "translate(0, 0) rotate(90deg) scale(1)"
    },
    '100%': {
      opacity: "1",
      border-radius: "5px"
      "-webkit-border-radius": "5px"
      transform: "translate(100px, 50px) rotate(180deg) scale(2)"
      "-webkit-transform": "translate(100px, 50px) rotate(180deg) scale(2)"
    }

$('#animation').css({
  'animation-name': 'anim',
  'animation-duration': '5s'
  'animation-timing-function': 'linear'
  'animation-delay': '1s'
  'animation-fill-mode': 'both'
});
```

---

# めんどくさい(2回目)

---

## keyframe-animations.js ｶｯｺｶﾘ

TODO: URL

- 作りました
- ベンダープレフィックスはお任せください
- transform functionをオブジェクトのキーにできます
- アニメーションのプロパティも一緒に渡せます

--

## keyframe-animations.js ｶｯｺｶﾘ

- アニメーションのライブラリを作ったりして運用しています(するつもりです)
```
TODO: こんなの
```

---

# ご清聴ありがとうございました

---
