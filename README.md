## Introducere
Aplicatia dezvoltata utilizeaza resurse de stocare puse la dispozitie de Google Cloud Platform (mai exact o baza de date SQL), avand ca scop principal exemplificarea utilizarii Google Natural Language API. 
## Descriere problemă 
Subdomeniu al inteligenței artificiale și lingvisticii, prelucrarea limbajului natural (Natural Language Processing, abreviat NLP) reprezintă o abordare computerizată a analizei textului, care se bazează interacțiunea dintre calculator și limbajul uman pentru procesarea datelor. În alte cuvinte, în ziua de astăzi este necesar ca datele de tip text sau chiar audio să fie interpretate de calculatoare, iar aici intervine NLP.
In scop demonstrativ, am utilizat API-ul furnizat de Google pentru a realiza sentiment analysis asupra unui text introdus de utilizator.
## Descriere API 
Google Natural Language API este o interfață ușor de utilizat pentru un set de modele NLP puternice, care au fost pregătite în prealabil de Google pentru a îndeplini diverse sarcini. Deoarece aceste modele au fost instruite pe texte ale unor documente de mari dimensiuni, performanța lor este de obicei destul de bună atâta timp cât sunt utilizate pe seturi de date care nu folosesc un limbaj idiosincratic.
Cel mai mare avantaj al utilizării acestor modele pre-antrenate prin intermediul API-ului este că nu este nevoie de un set de date de antrenament. API-ul permite utilizatorului să înceapă imediat să facă predicții.
API-ul Natural Language cuprinde cinci servicii diferite:
o	Analiza sintaxei
o	Analiza sentimentelor
o	Analiza entității
o	Analiza Sentimentului Entității
o	Clasificarea textului

Analiza sentimentelor va oferi opinia emoțională predominantă într-un text furnizat. API-ul returnează două valori: „Scorul” descrie înclinarea emoțională a textului de la -1 (negativ) la +1 (pozitiv), 0 fiind neutru, in timp ce „magnitudinea” măsoară puterea emoției.
## Flux de date
Componenta de backend include metodele CRUD specifice, desi interfata nu le utilizeaza pe toate.
Metodele HTTP utilizate in cele din urma sunt GET si POST, acestea aliniindu-se cu scopul aplicatiei.
Metoda GET care face posibila preluarea din baza de date a informatiilor referitoare la textele introduse de utilizatori:
![image](https://user-images.githubusercontent.com/44543705/168165971-de76f630-a03d-4f4b-a51c-692a53c38147.png)

Pentru testarea rutei, un exemplu de request/response poate fi observat mai jos:
 
Metoda POST creeaza o noua inregistrare in baza de date, totodata incluzand metoda ce analizeaza textul. Astfel, la momentul introducerii textului de catre utilizator, scorul este si el salvat automat in baza de date.
 
Pentru aceasta metoda, un exemplu de request/response este urmatorul:
 
Strict pentru testarea API-ului, am creat o metoda GET, care afiseaza scorul textului primit in request body.
 
## Capturi ecran aplicație 
Aplicatia este de tipul Single Page App, interfata fiind implementata in framework-ul React, iar stilizarea componentelor a fost facuta cu ajutorul bibliotecii Material UI.
 
Utilizatorii trebuie sa completeze numele si sa insereze continutul textului in campurile aferente, iar butonul central va realiza analiza textului introdus. Ulterior, aceasta va aparea sub forma unui card in lista din partea inferioara a ecranului.
 
Componenta care pastreaza detaliile referitoarele la textele introduse pe platforma afiseaza scorul textului, dar si daca sentimentul transmis este unul pozitiv sau negativ.

## Referințe
https://cloud.google.com/natural-language
https://www.toptal.com/machine-learning/google-nlp-tutorial
https://mui.com/material-ui/getting-started/installation/

