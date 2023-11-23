# createSelectOnDynamicOptions

### [githubpage](https://soonya27.github.io/createSelectOnDynamicOptions/)



### HTML
```html
    <select name="" id="selectAgency" class="form">
    </select>
```


### JS code
```javascript

 const options = [
            { text: 'options1', value: 1 },
            { text: 'options2', value: 2 },
            { text: 'options3', value: 3 },
            { text: 'options4', value: 4 }
        ];
  selectInit('#selectAgency', options, '타입선택');


 //vallila JS
/**
 * @param {string} id
 * @param {Array[{}]} options  -> [{text :'string' , value : num }]
 * @param {string} defaultText  -> optional
 */
function selectInit(id, options, defaultText) {
    const element = document.querySelector(id);
    element.innerHTML = '';
    if (defaultText != '') {
        const optionElement = document.createElement('option');
        optionElement.selected = true;
        optionElement.disabled = true;
        optionElement.innerHTML = defaultText;
        element.append(optionElement);
    }

    const optionAll = document.createElement('option');
    optionAll.innerHTML = '전체';
    element.append(optionAll);
    options.forEach(function (item) {
        const optionElement = document.createElement('option');
        optionElement.value = item.value;
        optionElement.innerHTML = item.text;
        element.append(optionElement);
    });
}


//jquery
// function selectInit(id, options, defaultText) {
//     $(id).empty();
//     if (defaultText != '') {
//         $(id).append(`<option selected disabled>${defaultText}</option>`);
//     }
//     $(id).append(`<option value="">전체</option>`)
//     options.forEach(function (item) {
//         $(id).append(`<option value="${item.value}">${item.text}</option>`);
//     });
// }
```
