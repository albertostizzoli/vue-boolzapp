ESERCIZIO DI OGGI: Vue Boolzapp

## MILESTONE 1:
- Replica della grafica con la possibilità di avere messaggi scritti dall’utente (verdi) e dall’interlocutore (bianco) assegnando due classi CSS diverse;
- Visualizzazione dinamica della lista contatti: tramite la direttiva v-for, visualizzare nome e immagine di ogni contatto;

- inizializzazione vue
- variabile per array contatti in vue
- tutto html layout
- v-for per lista contatti in left sidebar

## MILESTONE 2:
- Visualizzazione dinamica dei messaggi: tramite la direttiva v-for, visualizzare tutti i messaggi relativi al contatto attivo all’interno del pannello della conversazione;
- Click sul contatto mostra la conversazione del contatto cliccato;

- variabile per activeContact: 0 per visualizzare messaggi
- v-for per messaggi del contatto selezionato in main
- evento click su contatto esegue funzione showMessages
- funzione showMessages prende index / id del contatto cliccato e lo salva come activeContact


## MILESTONE 3:
- Aggiunta di un messaggio: l’utente scrive un testo nella parte bassa e digitando “enter” il testo viene aggiunto al thread sopra, come messaggio verde;
- Risposta dall’interlocutore: ad ogni inserimento di un messaggio, l’utente riceverà un “ok” come risposta, che apparirà dopo 1 secondo;

- variabile newMessage in data()
- input + bottone invio in html
- event click su bottone esegue funzione addNewMessage() 
- funzione crea nuovo oggetto message da inserire tra i messaggi di activeContact ( this.contacts[activeContact].messages.push( message ) )
- setTimeout con risposta ( nuovo oggetto da inserire tra i messaggi )


## MILESTONE 4:
- Ricerca utenti: scrivendo qualcosa nell’input a sinistra, vengono visualizzati solo i contatti il cui nome contiene le lettere inserite (es, Marco, Matteo Martina -> Scrivo “mar” rimangono solo Marco e Martina);

- variabile filterContact in data()
- input + bottone invio in html
- event keyUp esegue funzione filterContacts()

#### 1a soluzione
- filterContacts if filterContact != '' -> foreach(): se l'item inizia con la stringa in 
filterContact facciamo visible = true, else false. 
- in html modifichiamo la classe del singolo contatto :class= if visibile = false -> display none

#### 2a soluzione
- filterContacts if filterContact != '' -> filter() { se l'item contiene con la stringa in 
filterContact }
- in html non facciamo vedere più l'array originale ma l'array filtrato.



## MILESTONE 5(opzionale):
- Cancella messaggio: cliccando sul messaggio appare un menu a tendina che permette di cancellare il messaggio selezionato;
- Visualizzazione ora e ultimo messaggio inviato/ricevuto nella lista dei contatti;

- variabile clickedMessageID = null in data()
- nel v-for ci deve essere l'index
- event click su msg apre menu 
- cambia clickedMessageID = index del messaggio
- click su "delete" esegue funzione deleteMessage
- console.log in deleteMessage
- usare clickedMessageID per cancellare il messaggio dall'array di messaggi di activeContact ( contacts[activeContact].messages[clickedMessageID] = messaggio singolo da cancellare )


## CONSIGLI UTILI:
- Si possono trascurare le scrollbar verticali, sia nel pannello dei messaggi, che nella lista dei contatti;
- I pulsanti e le icone possono non funzionare (a parte l’invio del messaggio);
- Per gestire le date, può essere utile la libreria Luxon;



