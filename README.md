![lovetype](https://user-images.githubusercontent.com/110226567/213995722-33844b26-07e0-4baa-be32-4e5fe0f44eb1.png)

# π Twelve love type

12κ°μ§ μ°μ  μ ν μ¬λ¦¬ νμ€νΈ μ¬μ΄νΈ π [Demo](https://imjone.github.io/twelvelovetype/)

<br />

## π’ νλ‘μ νΈ κ°μ

12κ°μ§ μ§λ¬Έμ ν΅ν΄ λμ μ°μ  μ νκ³Ό κ°μ₯ μ΄μΈλ¦¬λ λλ¬Όμ μμλ³Ό μ μλ μ¬μ΄νΈμλλ€.<br />
μ΅κ·Ό SNS μμμ λ€μν ννλ‘ κΎΈμ€ν μ ννκ³  μλ MBTI νμ€νΈλ₯Ό λͺ¨ν°λΈλ‘ νκ³  μμΌλ©°,<br />
νΈλΆνΈ μμ΄ λ¨λλΈμ λͺ¨λ  μ°λ Ήλκ° μ¦κΈΈ μ μλ 'μ°μ 'λΌλ μ£Όμ λ₯Ό μ‘κ³  μ§ννκ² λμμ΅λλ€.

<br />

## π¨οΈ μ¬μ© κΈ°μ 

<p>
  <img src="https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=HTML5&logoColor=white"/>
  <img src="https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=CSS3&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=JavaScript&logoColor=white"/>
  <img src="https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=Bootstrap&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kakao Share API-FFCD00?style=flat-square&logo=KakaoTalk&logoColor=black"/>
</p>

<br />

## π μ£Όμ κΈ°λ₯

- 12κ°μ μ§λ¬Έλ§λ€ 3κ°μ λ΅λ³ μ νμ§ μ κ³΅
- νμ΄μ§ μλ¨μ νμ¬ νμ€νΈ μ§νλ₯ λ° νμ
- λ΅λ³ λ°μ΄ν°λ₯Ό λΆμνμ¬ μλ§λ κ²°κ³Ό λμΆ
- μΉ΄μΉ΄μ€ν‘ λ©μμ§λ₯Ό ν΅ν΄ νμ€νΈ κ²°κ³Ό κ³΅μ 
- λΆνΈμ€νΈλ©μ μ¬μ©ν λ°μν λμμΈ μμ

<br />

## π» μμ€ μ½λ

μ μ²΄ μ½λ λ³΄λ¬ κ°κΈ° π [Notion](https://imjone.notion.site/Twelve-love-type-1889c7cd3b084a5ba8196bf05de98ffb)

### π μ§λ¬Έ μ κ³΅νκΈ°

μ μ²΄ μ§λ¬Έμ§λ μΈλΆ νμΌμ `qnaList` λΌλ λ°°μ΄λ‘ λ―Έλ¦¬ μ μλμ΄ μμ΅λλ€.<br />
`goNext` ν¨μλ μΈμλ‘ μ λ¬ λ°μ μλ²μ ν΄λΉνλ μ§λ¬Έμ§λ₯Ό νλ©΄μ λ λλ§ν΄μ£Όλ ν¨μμλλ€.<br />
μ΄ν μ μ ν λ΅λ³μ§ μ κ³΅μ μν΄ λ΅λ³ λ¦¬μ€νΈμ μ§λ¬Έ μμλ₯Ό μΈμλ‘ μ λ¬νμ¬ `chooseAnswer`λ₯Ό νΈμΆν©λλ€.

```javascript
const questionBox = document.querySelector('.question-box');
const endPoint = 12; // μ΄ μ§λ¬Έ κ°μ

function goNext(qIndex) {
	if (qIndex === endPoint) {
    resultBtn.style.opacity = 1;
    resultBtn.style.pointerEvents = 'auto';
    resultBtn.addEventListener('click', goResult);
    return;
  }

  questionBox.innerText = `Q. ${qnaList[qIndex].q}`; // μ§λ¬Έ λ¦¬μ€νΈ
  for (let i in qnaList[qIndex].a) {
    const answer = qnaList[qIndex].a[i].answer; // λ΅λ³ λ¦¬μ€νΈ
    chooseAnswer(answer, qIndex, i);
  }
}
```

### π λ΅λ³ μ ννκΈ°

`chooseAnswer` ν¨μλ λ΅λ³ λ¦¬μ€νΈλ₯Ό λμ μΌλ‘ μμ±νμ¬ νλ©΄μ λ λλ§ν΄μ£Όλ ν¨μμλλ€.<br />
μ΅μ’ κ²°κ³Ό λμΆμ μν΄μ κ°κ°μ λ΅λ³μ§λ§λ€ ν΄λΉνλ λλ¬Όμ μ νμ΄ λͺ κ°μ§ μ§μ λμ΄ μμΌλ©°,<br />
μ¬μ©μκ° μ νν λ΅λ³μ `type` μΉ΄μ΄νΈκ° 1μ© μ¦κ°λμ΄ `selected` λ°°μ΄μ λ΄κΈ°κ² λ©λλ€.

```javascript
const selected = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0];

function chooseAnswer(answer, qIndex, aIndex) {
  const answerBox = document.querySelector('.answer-box');
  const answerBtn = document.createElement('button');
  answerBtn.classList.add('answer-list', 'mt-3', 'p-3');
  answerBox.appendChild(answerBtn); // λ΅λ³ λ¦¬μ€νΈ λμ  μμ±
  answerBtn.innerText = answer; // λ΅λ³ λ¦¬μ€νΈ μ½μ

  answerBtn.addEventListener('click', () => {
    const childrens = document.querySelectorAll('.answer-list');
    childrens.forEach(children => {
      children.disabled = true;
      children.style.WebkitAnimation = 'fadeOut 500ms';
      children.style.animation = 'fadeOut 500ms';
    });
    setTimeout(() => {
      // μ¬μ©μκ° μ νν λ΅λ³μ type count 1μ© μ¦κ°
      const type = qnaList[qIndex].a[aIndex].type;
      for (let i = 0; i < type.length; i++) selected[type[i]] += 1;
      childrens.forEach(children => children.remove());
      goNext(++qIndex); // λ€μ μ§λ¬Έ μ λ¬
    }, 450);
  });
}
```

### π νμ€νΈ κ²°κ³Ό κ³μ°νκΈ°

`calcResult` ν¨μλ κ°μ₯ λ§μ μΉ΄μ΄νΈκ° μμΈ λλ¬Ό μ νμ λ°νν΄μ£Όλ ν¨μμλλ€.<br />
`selected` λ°°μ΄μμ μ΅λκ°μ κ°μ§κ³  μλ μμκ° κ³§ μ΅μ’ κ²°κ³ΌλΌκ³  λ³Ό μ μκ² μ΅λλ€.

```javascript
function calcResult() {
  const typeResult = selected.indexOf(Math.max(...selected));
  return typeResult;
}
```

<br />

## π λ°°μ΄ μ  λ° λλ μ 

- νλ‘μ νΈλ₯Ό μ§ννλ©΄μ λ°°μ΄μ μ΄λ€ μμΌλ‘ νμ©ν  μ μλμ§ κ°μ μ‘°κΈ λ μ΅ν μ μμμ΅λλ€.
- κ²°κ³Ό νμ΄μ§λ₯Ό λ κ°λ¨νκ² λ§λ€μ΄λ³Ό μ μμμ κ² κ°μλ° μμ§ κ·Έ λ°©λ²κΉμ§λ μκ°ν΄λ΄μ§ λͺ»ν΄ μμ½μ΅λλ€.
- μνλ μλλλ‘ μ λλ©μ΄μμ΄ λμνμ§ μμ κ½€ μ λ₯Ό λ¨Ήμμ΅λλ€. μ λλ©μ΄μ λν μ½μ§ μμ κΈΈμ΄λΌλ κ±Έ λκΌμ΅λλ€..
- μμλ€μ κ³μ λμ μΌλ‘ μμ±νλ€ λ³΄λ ν·κ°λ¦¬λ λΆλΆμ΄ λ§μμ΅λλ€. λΌλ¦¬μ  μ¬κ³  λ₯λ ₯μ μ€μμ±μ λ€μ ν λ² κΉ¨λ¬μμ΅λλ€.
