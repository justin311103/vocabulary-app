# vocabulary-app
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>背單字程式</title>

<style>
body{
    text-align:center;
    font-family:Arial;
    margin-top:100px;
}

#word{
    font-size:40px;
    margin:20px;
}

#meaning{
    font-size:25px;
    margin:20px;
}

button{
    padding:10px 20px;
    font-size:18px;
    margin:10px;
}
</style>

</head>
<body>

<h1>英文單字練習</h1>

<div id="word"></div>
<div id="meaning"></div>

<button onclick="showMeaning()">顯示答案</button>
<button onclick="nextWord()">下一題</button>

<script>
const words = [
    {english:"apple", chinese:"蘋果"},
    {english:"banana", chinese:"香蕉"},
    {english:"computer", chinese:"電腦"},
    {english:"school", chinese:"學校"},
    {english:"beautiful", chinese:"美麗的"}
];

let current = 0;

words.sort(() => Math.random() - 0.5);

function loadWord(){
    document.getElementById("word").innerText =
    words[current].english;

    document.getElementById("meaning").innerText = "";
}

function showMeaning(){
    document.getElementById("meaning").innerText =
    words[current].chinese;
}

function nextWord(){
    current++;

    if(current >= words.length){
        alert("完成全部單字！");
        current = 0;
        words.sort(() => Math.random() - 0.5);
    }

    loadWord();
}

loadWord();
</script>

</body>
</html>
