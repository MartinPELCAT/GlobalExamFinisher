# GlobalExamFinisher
Script pour faire les 3 heures et 10 activités de Global Exam

Sur la page https://exam.global-exam.com/library/study-sheets/categories/grammar
Dans la console : 
**Si un seul s'ouvre, il faut Autoriser chrome a ouvrir plusieurs popups**

![image](https://user-images.githubusercontent.com/35460122/144402666-d2b8535e-f0ca-47c5-8049-82a0545f4e52.png)


```javascript
const buttons = document.querySelectorAll("a.button-solid-primary-small");
for (let index = 0; index < 40; index++) {
  setTimeout((idx) => {
    window.open(buttons[idx].href);
  }, index * 1000, index);
}
```
