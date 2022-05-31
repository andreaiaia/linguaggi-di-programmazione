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

    Una derivazione si dice sinistra/destra se ad ogni passo viene riscritto il non-terminale piu a sinistra/destra della stringa.
    Derivazione sinistra e destra generano lo stesso albero

    ***

    Sì: se due derivazioni sinistre/destre per uno stesso $NT$ sono diverse, allora al $NT$ più a sinistra sono stato applicate due produzioni diverse e quindi due alberi di derivazione diversi.

<br>

21. `Quando una grammatica è ambigua? (fare un esempio) Quando un linguaggio è ambiguo? (fare un esempio)`

    Una grammatica $G$ è ambigua se $\exist$ almeno una stringa di $L(G)$ che ammette più di un albero di derivazione. Ad esempio la grammatica delle espressioni è ambigua.

    Un linguaggio è ambiguo quando tutte le grammatiche che lo generano sono ambigue.

<br>

22. _È possibile rimuovere l’ambiguità dalla grammatica delle espressioni aritmetiche? Come?_

    Spesso è possibile modificare una grammatica ambigua per ottenere una versione non ambigua che fa uso di _zucchero sintattico_, ad esempio stabilendo delle regole di precedenza nelle derivazioni o manipolando la grammatica.

<br>

23. `Cos’è l’albero di sintassi astratta? Che differenza c’è tra sintassi concreta e sintassi astratta? Cos’è lo zucchero sintattico?`

    L'albero di sintassi astratta è un albero di derivazione che soddisfa i vincoli contestuali di un linguaggio in cui compaiono solo terminali $T$.

    La sintassi astratta è composta da una grammatica semplice ma ambigua. La sintassi concreta è una grammatica non ambigua che fa uso di zucchero sintattico (per eliminare l'ambiguità)

    Lo zucchero sintattico è l'uso di simboli con lo scopo di chiarire la derivazione di una stringa (ad esempio usando parentesi).

<br>

24. `Fare esempi di vincoli sintattici contestuali. Possono essere catturati attraverso grammatiche libere?`

    I vincoli sintattici contestuali sono regole la cui correttezza può essere verificata sul testo di un programma, ad esempio il numero ed il tipo dei parametri attuali di una chiamata di funzione deve corrispondere a quelli definiti nella dichiarazione, oppure una variabile può essere usata solo dopo essere stata dichiarata.

    Risposta 2

<br>

25. `Cosa s’intende per semantica statica? E per semantica dinamica?`

    La semantica statica è l'insieme di regole di correttezza che possono essere verificate sul testo di un programma (a compile-time), mentre la semantica dinamica è l'insieme delle regole la cui correttezza può essere verificata solo a run-time e per questo essa è una rappresentazione formale dell'esecuzione del programma.

<br>

26. `Elencare le varie fasi in cui si articola un compilatore. Descrivere in dettaglio ogni singola fase.`

    - **Analizzatore lessicale** (scanner):

      Questa fase controlla che gli operatori e la sintassi siano corretti, lo fa avvalendosi di una symbol table, controlla che gli identificatori siano corretti e che il lessico sia ammissibile. Riempie parzialmente la symbol table con identificatori di variabili, procedure, ecc.

      - OUTPUT: **lista dei token**.

    - **Analizzatore sintattico** (parser):

      Prende la lista dei token e costruisce l'albero di derivazione, consulta di nuovo la symbol table e interagisce con il gestore degli errori.

      - OUTPUT: **l'albero di derivazione** del programma.

    - **Analizzatore semantico**:

      Esegue dei controlli di semantica statica per rivelare eventuali errori. Arricchiste l'albero di derivazione con informazioni sui tipi e genera eventuali messaggi di errore.

      - OUTPUT: **l'albero di derivazione aumentato**.

    - **Generatore della forma intermedia**:

      In questa fase il compiler costruisce un programma in un linguaggio intermedio molto semplice, non specifico per un'architettura e traducibile in linguaggio macchina di varie macchine diverse (easy to produce, easy to translate). Questo codice deve essere manipolato ancora perché inefficiente.

      - OUTPUT: **programma in linguaggio intermedio**.

    - **Ottimizzatore**:

      In questa fase il codice intermedio viene ottimizzato per aumentarne l'efficienza (rimozione di codice inutile, espansione delle chiamate di funzione, estrazione dai cicli delle parti che non variano, ecc).

      - OUTPUT: **codice intermedio ottimizzato**.

    - **Generatore del codice finale**:

      In questa fase viene infine generato il codice per l'architettura specifica.

      - OUTPUT: **programma compilato**.

<br>

27. _A chi serve definire la semantica di un linguaggio e perché?_

    Serve al programmatore fare analisi del programma, per capirne a fondo il funzionamento; serve al progettista di linguaggio per poter specificare cosa fa il linguaggio e mostrarne le proprietà. Coniuga la necessità di esattezza e quella di flessibilità.

<br>

28. _Quali tecniche si usano per dare semantica ad un linguaggio di programmazione?_

    Ci sono due grandi famiglie di tecniche:

    - Semantiche **denotazionali**:

      Ovvero l'applicazione ai linguaggi di programmazione di tecniche sviluppate per la semantica del linguaggio logico-matematico. Il significato del programma è dato da una funzione che esprime il comportamento del programma stesso.

    - Semantiche **operazionali**:

      La semantica operazionale specifica il comportamento di una macchina astratta (ne definisce l'interprete), facendo riferimento ad un formalismo di livello più basso.

<br>

29. ` Imparare le regole di semantica operazionale strutturata per il semplice linguaggio presentato a lezione. Regole di valutazione interna-sinistra ed esterna-sinistra.`

    Di seguito le regole di sos delle espressioni aritmetiche, per la quale è necessario definire un sistema di transizione $<\Gamma_e,T_e,\rarr_e>$ dove:

    - $\Gamma_e = \{\langle e,\sigma\rangle|e\in Exp,\sigma\in Store\}$ è l'insieme degli stati possibili;
    - $T_e = \{\langle n,\sigma\rangle|n\in\N,\sigma\in Store\}$ è l'insieme degli stati terminali;
    - $\rarr_e$ è la minima relazione che soddisfa gli assiomi e le regole di inferenza.

    > _Nota_:
    >
    > In $\Gamma_e$ si trovano le coppie formate da un espressione a cui associamo uno store, come se sapessimo che il risultato dell'espressione verrà salvato nella variabile.
    >
    > In $T_e$ si fa la stessa cosa ma c'è un numero associato allo store, quindi la variabile ha un valore finito.

    **Le regole di inferenza sono**:

    - $Var$: $\cfrac{-}{\langle v,\sigma\rangle\rarr_e\langle\sigma(v),\sigma\rangle}$;
    - $Sum1$: $\cfrac{\langle e_0,\sigma\rangle\rarr_e\langle e_0',\sigma'\rangle}{\langle e_0+e_1,\sigma\rangle\rarr_e\langle e_0'+e_1,\sigma'\rangle}$;
    - $Sum2$: $\cfrac{\langle e_1,\sigma\rangle\rarr_e\langle e_1',\sigma'\rangle}{\langle m+e_1,\sigma\rangle\rarr_e\langle m+e_1',\sigma'\rangle}$;
    - $Sum3$:$\cfrac{-}{\langle m+m',\sigma\rangle\rarr_e\langle p,\sigma\rangle}$.

<br>

30. _Cosa s’intende per pragmatica? Cosa si intende per implementazione di un linguaggio?_

    Per pragmatica si intende il modo corretto di utilizzare un costrutto corretto. La pragmatica non è quindi stabilita una volta per tutte all'atto di definizione di un linguaggio ma evolve assieme all'uso che viene fatto di quel linguaggio.
