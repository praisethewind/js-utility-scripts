// ==UserScript==
// @name         GoogleForm Spammer
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  Spam a Google Form
// @author       vsachev
// @match        https://docs.google.com/forms/*
// @grant        unsafeWindow
// ==/UserScript==

(function() {
        setTimeout(() => {
            submitRandomForm();
        }, 1000);

        function submitRandomForm() {
            document.querySelectorAll('.freebirdFormviewerComponentsQuestionBaseRoot').forEach(elem => {
                var radios = elem.querySelectorAll('.appsMaterialWizToggleRadiogroupRadioButtonContainer')
                if (radios.length > 0) {
                    var random = Math.floor(Math.random() * radios.length);
                    if (radios[random].parentElement.parentElement.parentElement.childNodes[1].firstElementChild.firstElementChild.innerText == 'Другое:') {
                        random = Math.floor(Math.random() * (radios.length - 1));
                    }
                    radios[random].click();
                }
                var checkboxes = elem.querySelectorAll(".appsMaterialWizTogglePapercheckboxCheckbox");
                if (checkboxes.length > 0) {
                    var m = Math.floor(Math.random() * 5 + 1)
                    for (var i = 0; i < m; i++ ){
                        var random2 = Math.floor(Math.random() * checkboxes.length);
                        if (checkboxes[random2].parentElement.childNodes[1].firstElementChild.firstElementChild.innerText == 'Другое:') {
                            random2 = Math.floor(Math.random() * (checkboxes.length - 1));
                        }
                        checkboxes[random2].click();
                    }
                }

                var end = document.querySelectorAll('.appsMaterialWizButtonPaperbuttonLabel');
                if (end.length > 0) {
                    setTimeout(() => {
                        end[end.length - 1].click();
                    }, 1000)
                }
            });
            if (document.querySelectorAll('.freebirdFormviewerViewResponseLinksContainer').length > 0) {
                document.querySelectorAll('.freebirdFormviewerViewResponseLinksContainer')[0].firstElementChild.click();
            }
        }

})();
