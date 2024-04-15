# 15_JS_practice
 2024前期「JavaScript演習」リポジトリ

##　オブジェクトとクラス
　　4月１５日（月）
 ///もっと簡単なオブジェクトを作ってみる
 const dict = { apple: "りんご", banana: "バナナ", orange: "オレンジ" };
 console.log(dict.apple);
console.log(dict["apple"]);
dict.grape = "ぶどう";
console.log(dict);



///オブジェクトとオブジェクトの操作
<p id="result"></p>
const demaeicchou = {
  name: "出前一丁",
  soup: "醤油",
  preview: function () {
    const area = document.querySelector("#result");
    area.innerHTML = `${this.name}は、${this.soup}ラーメンです。`;
  },
};
demaeicchou.preview();
書き換えや追加、削除が簡単にできます。

demaeicchou.soup = "とんこつ";
demaeicchou.preview = function () {
  const area = document.querySelector("#result");
  area.innerHTML = `${this.name}は、${this.soup}ラーメンではありません。`;
};
delete demaeicchou.name;

demaeicchou.preview();



///インスタンスの生成
const soltRamen = new InstantNoodle("サッポロ一番塩", "塩");
const demaeicchou = new InstantNoodle("出前一丁", "醤油");

//メソッドの呼び出し
class InstantNoodle {
  constructor(ramen, taste) {
    this.name = ramen;
    this.soup = taste;
  }
  descript() {
    return `<p>${this.name}は、${this.soup}味です。</p>`;
  }
}