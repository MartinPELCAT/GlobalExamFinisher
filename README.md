# GlobalExamFinisher

Sur la page "Parcours"

Il faut peut etre augmenter la valeur du timeout apres le lignes ci-dessous

```
btn.click();
activityTimeout = null;
```


Dans la console : 
```javascript
const button = document.querySelector(
  ".button-outline-default-medium, .button-solid-primary-medium"
);
button.click();
var body = document.body;

var config = {
  childList: true,
  subtree: true
};

let activityTimeout = null;
let startAcivityObserver = new MutationObserver(function (mutations) {
  mutations.forEach(function () {
    if (activityTimeout) clearTimeout(activityTimeout);
    activityTimeout = setTimeout(function () {
      const btn = document.querySelector(".button-solid-primary-large");
      const quit = document.querySelector('a[href="/"]')
      if (quit) {
        quit.click()
        startAcivityObserver.disconnect();
        restartObserver.observe(body, config);
        activityTimeout = null;
        return;
      }
      btn.click();
      activityTimeout = null;
    }, 2000);
  });
});

let restartTimeout = null;
let restartObserver = new MutationObserver(function (mutations) {
  mutations.forEach(function () {
    if (restartTimeout) clearTimeout(restartTimeout);
    restartTimeout = setTimeout(function () {

      document.querySelector('span[data-title="Parcours"]').click();
      restartObserver.disconnect();
      setTimeout(function () {
        const btn = document.querySelector(
          ".button-outline-default-medium, .button-solid-primary-medium"
        );
        btn.click();
        setTimeout(function () {
          startAcivityObserver.observe(body, config);
        }, 1000);
      }, 1000);
    }, 500);
  });
});


let pageTimeout = null;
let changePageObserver = new MutationObserver(function (mutations) {
  mutations.forEach(function () {
    if (pageTimeout) {
      clearTimeout(pageTimeout);
    }
    pageTimeout = setTimeout(function () {
      changePageObserver.disconnect();
      document.querySelector(".button-solid-primary-large").click();
      setTimeout(function () {
        startAcivityObserver.observe(body, config);
      }, 1000);
    }, 1000);
  });
});

changePageObserver.observe(body, config);
```

![image](https://user-images.githubusercontent.com/35460122/148954134-fb887381-0166-4ce1-83f9-2e6ee8e21522.png)
