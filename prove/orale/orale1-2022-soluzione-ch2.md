# Domande e Risposte orale modulo 1 - capitolo 2

Ndr: le domande `evidenziate` sono quelle da sapere per passare l'esame (citando il prof: "se non sapete rispondervi non presentatevi nemmeno"), le altre domande non sono così determinanti ma saperle non fa male.

## Capitolo 2 - Descrivere un linguaggio di programmazione

15. `Quali sono i livelli di descrizione di un linguaggio?`

    - Grammatica:

      La grammatica risponde alla domanda "quali frasi sono corrette?" ed è formata da due stadi fondamentali:

      - **Lessico**: ovvero l'insieme delle parole che posso usare, il **dizionario**;
      - **Sintassi**: ovvero le **regole** da seguire per costruire frasi corrette.

    - Semantica:

      È la parte che prova a rispondere alla domanda "cosa significa una frase corretta?", quindi è la parte che dà un significato ad una frase. A tal proposito è importante conoscere la lingua di appartenenza della parola.

    - Pragmatica:

      È quella parte del linguaggio che risponde alla domanda "come usare una frase corretta e sensata?", ovvero studia l'utilizzo delle frasi e il modo in cui vengono usate nel contesto.

    Infine, nel caso dei linguaggi di programmazione c'è anche

    - Implementazione:

      Risponde alla domanda "come eseguire una frase corretta, in modo da rispettarne la semantica?".

<br>

16. _Sintassi: qual è l’aspetto lessicale e quale quello grammaticale di un linguaggio?_

    L'aspetto lessicale è il modo di costruire dei **token** a partire da caratteri dell'alfabeto.

    L'aspetto grammaticale è il modo di costruire "frasi" legali a partire da tali token.

<br>

17. _Cos’è un alfabeto? Cos’è una parola o stringa?_ `Cos’è A*?` _Tale insieme è contabile?_

    Un alfabeto è un insieme di simboli.

    Una parola (o stringa) è una sequenza corretta di simboli appartenenti all'alfabeto.

    $A*$ è il piu grande linguaggio che posso costruire con i simboli dell'insieme $A$.

    $A*$ è un insieme infinito contabile.

<br>

18. _Definizione di potenza di una stringa. Definizione di chiusura/iterazione (o stella di Kleene) di un linguaggio._

    La potenza di una stringa è una stringa ripetuta n volte (con n che va da 0 a infinito) concatenate.

<br>

19. `Definizione di grammatica libera da contesto. Come si deriva una stringa? Qual è il linguaggio generato da una grammatica libera?`

    Una grammatica libera da contesto è una quadrupla ($NT, T, R, S$) dove:

    - $NT$: è l'insieme finito di simboli non terminali;
    - $T$: è l'insieme finito dei simboli terminali;
    - $S \in NT$: è il simbolo iniziale;
    - $R$: è l'insieme finito di produzioni (o regole), ciascuna espressa nella forma $v \rarr w$ dove $v \in NT$ e $w \in T \cup NT$.

    ***

    Fissata una grammatica $G$ e assegnate due stringhe $v, w$, diciamo che da $v$ si deriva immediatamente $w$ se $w$ si ottiene da $v$ sostituendo ad un $NT$ $V$ in $v$ il corpo di una produzione la cui testa sia $V$. Diciamo che da $v$ si deriva $w$ se esiste una sequenza finita di derivazioni immediate che porta da $v$ a $w$.

    ***

    Il linguaggio generato da una grammatica libera è l'insieme $L(G)=w\in T^*|S\rarr^*w$, ovvero l'insieme delle stringhe finite ottenibili dal simbolo iniziale $S$ con una o più derivazioni sui terminali.

<br>

20. `Cos’è un albero di derivazione? Cos’è una derivazione canonica sinistra/destra? Esiste una corrispondenza biunivoca tra alberi di derivazioni e derivazioni canoniche?`

    Data una grammatica libera, un albero di derivazione è un albero ordinato in cui:

    - Ogni nodo è etichettato con un simbolo in $NT \cup T \cup \{\epsilon\}$;
    - La radice è etichettata con $S$;
    - Ogni nodo interno è etichettato con un simbolo in $NT$;
    - Se un certo nodo ha etichetta $A \in NT$ e i suoi figli sono $m_1, ..., m_k$ etichettati rispettivamente con $X_1, ..., X_k$ dove $X_i \in NT \cup T \forall i \in [1,k]$, allora $A\rarr X_1, ..., X_k$ è una produzione di $R$;
    - Se un nodo ha etichetta $\epsilon$ allora quel nodo è figlio unico e, detto $A$ il suo padre, $A\rarr\epsilon$ è una produzione di $R$.

    ***

    Risposta 2

    ***

    Risposta 3

<br>

21. `Quando una grammatica è ambigua? (fare un esempio) Quando un linguaggio è ambiguo? (fare un esempio)`

    Risposta

<br>

22. _È possibile rimuovere l’ambiguità dalla grammatica delle espressioni aritmetiche? Come?_

    Risposta

<br>

23. `Cos’è l’albero di sintassi astratta? Che differenza c’è tra sintassi concreta e sintassi astratta? Cos’è lo zucchero sintattico?`

    Risposta

<br>

24. `Fare esempi di vincoli sintattici contestuali. Possono essere catturati attraverso grammatiche libere?`

    Risposta

<br>

25. `Cosa s’intende per semantica statica? E per semantica dinamica?`

    Risposta

<br>

26. `Elencare le varie fasi in cui si articola un compilatore. Descrivere in dettaglio ogni singola fase.`

    Risposta

<br>

27. _A chi serve definire la semantica di un linguaggio e perché?_

    Risposta

<br>

28. _Quali tecniche si usano per dare semantica ad un linguaggio di programmazione?_

    Risposta

<br>

29. ` Imparare le regole di semantica operazionale SOS per il semplice linguaggio presentato a lezione. Regole di valutazione interna-sinistra ed esterna-sinistra.`

    Risposta

<br>

30. _Cosa s’intende per pragmatica? Cosa si intende per implementazione di un linguaggio?_

    Risposta
