---
layout: post
title: "Unity Basics #1: The Engine"
description: The very basics Unity steps
date:   2017-05-21 20:13:10 +0200
author: Gio-
permalink: /:categories/it/:title
hidden: true
lang: it

comments: true
categories: article
image: coffee.jpg
tags: unity, basics, unity basics, game, dev, programming, c#, c sharp, tutorials, tutorial
---

<div class="langSelection"><a href="{{ page.url| remove_first: "it/" | prepend: site.url}}">EN </a>| IT</div>



> **Nota**: Questa è la prima parte di una piccola serie, o come mi piace chiamarla, una *Rubrica*, che è stata scritta nel 2017 con Unity 5.4 - 5.6. Se sei un lettore che proviene dal futuro, probabilmente sarà obsoleta.



# Primi Passi In Unity

Unity è un motore grafico sviluppato dalla Unity Technologies che si occupa principalmente di creare videogiochi. Tale motore può essere scaricato seguendo i passaggi descritti nel link qui presente:

[Download Unity](https://store.unity.com/?).

Prima di iniziare a spiegare della programmazione, è utile sapere alcune *keywords* e aspetti di questo *engine*. In Unity, puoi programmare in 3 linguaggi di programmazione differenti:

- **Boo**: pls don't...
- **Javascript (sort of)**: non è propriamente javascripta ma <u>UnityScript</u>. Nelle precedenti versioni, era molto popolare e oggi si possono ancora trovare, da qualche parte nella rete, dei tutorial che utilizzano questo linguaggio. Tuttavia viene sempre meno utilizzato in favore di un linguaggio più solido e performante come il C#.
- **C#**: tra i più usati nella comunità di Unity. E' il più avanzato e ottimizzato tra Javascript e Boo, inoltre si interfaccia meglio con Obj e XCode. Sta diventando lo standard dei linguaggi di programmazione volti alla creazione di videogiochi. C# però possiede degli svantaggi che verranno trattati nei post successivi.

In questa Rubrica, scrivero il codice in C# partendo dalle basi.

## Tabs and Windows

Ci sono molteplici tabs in Unity, solitamente preferisco avere un layout che dia maggior visibilità alla tab *Scene* e *Game*, come qua sotto illustrato:

![unityframe]({{site.url}}/assets/2017-05-21-unity-basics-part-1/unityframe.jpg)

Clicca su `Layout` in alto a destra `Layout -> 2 by 3 Column` e poi `Tasto Destro su Project -> one column layout`.

### Scene

La finestra <u>Scene</u> ci permette di costruire la nostra scena in 2D o 3D modificando, spostando e ruotando i GameObjects.

![Scene Shortcuts]({{site.url}}/assets/2017-05-21-unity-basics-part-1/sceneShortcuts.jpg)

Puoi modificare i GameObject nella tua Scena cliccando i pulsanti posti in alto o sinistra, oppure attraverso queste shortcuts: Naviga nella scena <kbd>Q</kbd>, Sposta <kbd>W</kbd>, Ruota <kbd>E</kbd> e Scala <kbd>R</kbd>. Ci sono poi altre combinazioni utili quando si compone una scena:

- Navigation

|                                        |                                          |
| -------------------------------------- | ---------------------------------------- |
| <kbd>Left Click</kbd>                  | Muoviti a destra e sinistra su un punto. |
| <kbd>Right Click</kbd>                 | Ruota intorno al punto in cui sei fermo. |
| <kbd>Alt</kbd> + <kbd>Left Click</kbd> | Ruota intorno ad un punto selezionato.   |
| <kbd>Alt</kbd> + <kbd>RightClick</kbd> | Ingrandisci sul punto che stai guardando. |
| <kbd>F</kbd>                           | Focalizzati su un oggetto selezionato.   |


### Game

La *preview* del gioco si attiva premendo il tasto PLAY posto in alto al centro. Seguono il tasto PAUSE e STEP FORWARD. Quest’ultimo serve per scorrere il gioco frame per frame in modo da poter analizzare al meglio cosa succede nella scena. 

Attraverso l’inspector è possibile modificare i parametri al *Run Time* per visualizzare in tempo reale i comportamenti che il gioco assume con settaggi differenti. 

![Game Window]({{site.url}}/assets/2017-05-21-unity-basics-part-1/gameWindows.jpg)

Cliccando su FREE ASPECT si può cambiare la risoluzione e inserirne una specifica al tipo di piattaforma di riferimento. Per inserire una grandezza particolare, selezionare `EDIT > Project Setting > Player`. La nuova risoluzione sarà visibile in editor solo attraverso il <u>Maximaze on Play</u>. Con questo parametro attivo, tutte le volte che premiamo PLAY giocheremo a schermo intero. 
Infine, per tenere sotto controllo tutte le statistiche del gioco, dai frame per second (FPS) al numero di triangoli nella scena, basterà cliccare su <u>Stats</u>.

### Hierarchy

La Hierarchy, in Unity, è la lista completa di tutti gli oggetti che fanno parte della scena aperta nell’editor. Questi sono in ordine alfabetico e in ordine di “parenting”. È infatti possibile raggruppare degli oggetti sotto un unico “padre” attraverso un GameObject vuoto definito "Empty". 

Nella scena, creiamo un empty cliccando `Tasto Destro -> Create Empty`. Per raggruppare degli oggetti sotto un unico parent, basterà trascinarli dalla gerarchia sul nome di tale empty appena creato. I gameObject sotto un parent, verranno definiti come “Child”, o figli. 

Gli oggetti figli, hanno una caratteristica: il loro **Transform** si basa su quello del padre. Per far capire la differenza: quando un oggetto normale si sposta in una scena, si sposterà in base alla distanza dall’origine del mondo di Unity. Ma se questo sarà figlio di un altro, allora le sue coordinate saranno relative a quelle del padre e il suo origine di riferimento sarà, appunto, quello del padre stesso.

E’ sempre opportuno, quando si usa la tecnica del parenting solo per raggruppare oggetti, che l’empty padre di riferimento si trovi nella posizione 0, con rotazione 0, e scale 1. Per esserne certi, PRIMA di eseguire il parenting, basta premere `Tasto Destro -> Reset`.

> **Note**: Tutte le operazioni di rotation, scaling o positioning, se fatte sul GameObject padre, verranno eseguite anche sull’oggetto figlio.

Cliccando con `Tasto Destro` sulla hierarchy, è possibile creare degli oggetti nella scena. 

### Project

Il panello Project ci permette di visualizzare tutti gli assets del nostro gioco. E’ la copia della cartella *Assets* del progetto che puoi trovare attraverso il sistema operativo. Tuttavia è sconsigliato cancellare o spostare delle cartelle e file da sistema in quanto potrebbero corrompere i link che li collegano con Unity. 

E' possibile creare assets in 3 modi:

1. Cliccando con il `Tasto Destro` nel pannello Project.
2. Aggiungere o spostare file direttamente nella directory nella cartella Assets del nostro progetto.
3. Trascinarli nel pannello project.

Oltre a poter importare assets provenienti da altri progetti selezionando dalla toolbar `Assets -> Import New Assets`, possiamo anche vedere direttamente lo store di Unity nell'editor.

### Inspector

Il pannello Inspector in Unity permette di modificare tutte le proprietà di qualsiasi oggetto, assets o dell’editor.

![Inspector Panel]({{site.url}}/assets/2017-05-21-unity-basics-part-1/inspectorPanel.jpg)

Per gli oggetti,l’inspector inizia con:

- Titolo, il nome del GameObject all’interno dellascena.
- Un checkbox da selezionare se vogliamo che abbia particolari proprietà come *statico* nella scena.
- Menu a tendina per *Tag* o *Layers*.

Successivamente, vengono elencati tutti i component di un GameObject partendo dal Transform che mostra la rotazione, la posizione e lo scale di un oggetto.

In ogni component, l’inspector permette di modificare i valori in vari modi: tenendo premuto sul campo, potremmo scorrere l’input come se fosse uno slider; possiamo riscrivere il valore o decidere di resettarlo cliccando sulla rotellina in alto a destra del component e poi su Reset.

Unity ha una funzione di Drag & Drop per impostare determinati valori nell’inspector. Ad esempio, possiamo settare delle variabili pubbliche in uno script che saranno visibili in questo pannello e modificabili a nostro piacimento. Se una variabile fa riferimento ad un component di un altro oggetto in scena, possiamo trascinare quell’oggetto nel campo di tale variabile esposta nell’inspector e fornire così un assegnazione.

Tuttavia, potrebbe capitare di cliccare su altri oggetti e cambiare così l’inspector. La funzione Lock Inspector, posto in alto a destra del pannello a la forma di un lucchetto, eviterà questi problemi facendo rimanere la schermata fissa sull’oggetto selezionato.

Un’oggetto può essere disabilitato premendo il checkbox accanto al proprio nome, così come ogni suo componente. Una volta premuto PLAY possiamo modificare i valori di un oggetto in scena per poter vedere come cambia un suo comportamento in gioco. 

> **Note**: Una volta usciti dalla modalità PLAY, quei valori non verranno salvati. 

Cliccando `Tasto Destro `durante la modalità PLAY sul nome di un component e poi su `Copy Component `, una volta terminato il test, possiamo ricopiare tutto nei campi premendo di nuovo il tasto destro e `Paste Component Values `.

## Coordinates

Unity viene definito come un motore Y-up in quanto la Y è la coordinata spaziale rivolta verso l’alto.

![coordinate]({{site.url}}/assets/2017-05-21-unity-basics-part-1/coordinate.jpg){: .img-responsive }

Queste coordinate vengono anche chiamate:

- X = Right
- Y = Up
- Z = Forward

There are two types of coordinates in Unity:

1. **World** o <u>coordinate globali</u>, sono quelle fisse che non possono cambiare, fanno riferimento al “mondo” di unity.
2. **Local** ovvero le "coordinate dell’oggetto". Queste sono invece proprie dell’oggetto e cambiano in base ad esso. Per esempio, la coordinata Z ruoterà in base alla rotazione del GameObject. 

>**Nota**: Differenze con gli altri motori (Unreal Engine, ad esempio, è un motore Z-UP).

![difference Engine Coordinate]({{site.url}}/assets/2017-05-21-unity-basics-part-1/difference.jpg){: .img-responsive }

Nel prossimo episodio, parlerò dei GameObjects e i Components in Unity.



Grazie per la lettura.