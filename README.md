# GlobalExamFinisher
Script pour faire les 3 heures et 10 activités de Global Exam

Sur la page https://exam.global-exam.com/library/study-sheets/categories/grammar
**Si un seul s'ouvre, il faut Autoriser chrome a ouvrir plusieurs popups**

![image](https://user-images.githubusercontent.com/35460122/144402666-d2b8535e-f0ca-47c5-8049-82a0545f4e52.png)

Dans la console : 
```javascript
const buttons = document.querySelectorAll("a.button-solid-primary-small");
for (let index = 0; index < 40; index++) {
  setTimeout((idx) => {
    window.open(buttons[idx].href);
  }, index * 1000, index);
}
```

| Avant      | Après |
| ----------- | ----------- |
| ![image](https://user-images.githubusercontent.com/35460122/144404419-ae1cc48c-07b0-4c9e-aa30-9f1e92e1c454.png)| ![image](https://user-images.githubusercontent.com/35460122/144404442-ae381abb-6d83-4138-8367-f97be99fc83b.png) |
 
