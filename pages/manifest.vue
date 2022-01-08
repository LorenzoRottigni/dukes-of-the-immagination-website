<template lang="pug">
    .container-fluid.h-100.d-flex.align-items-stretch
        .row
            .col-12.col-lg-5.bg-dark.py-5.shadow-lg.d-flex.align-items-center
                //NAV-SIDE BAR
                nav#sidenav
                    ul.d-flex.flex-column.list-unstyled.gap-3.mb-0.text-white
                        //for each section print title in list item
                        //if the li is the current, color is gold
                        li(
                            :key="index+'-section'",
                            v-for="(section, index) in sections",
                            @click="setCurrentIndex(index)",
                            :style="(index === currentIndex)?{ color : 'gold' }:''"
                        )
                            //go to text-section
                            a.text-reset(href="#text-section")
                              i.fab.fa-artstation.mx-3.ml-0
                              | {{section.title}}
            //TEXT-SECTION
            #text-section.col-12.col-lg-7.bg-light
                //display current indexed title
                h1.text-center.mt-5.mb-3 {{sections[currentIndex].title}}
                //display current indexed paragraph
                .paragraphs-container.px-lg-5
                    p(:key="index+'-paragraph'" v-for="(paragraph, index) in sections[currentIndex].paragraphs")
                        | {{paragraph}}

</template>

<script>
  import gsap from "gsap"

  export default {
      data(){
          return {
              sections:[
                  {
                      title : 'La trappola di un presente immutabile',
                      paragraphs : [
                          "Il futuro non esiste, è solo la rappresentazione immaginifica di un presente alternativo che proiettiamo nelle nostre menti.",
                          "Se non prendiamo azione, se ci lasciamo solo trasportare dagli eventi senza mai prendere una posizione, se rimaniamo fermi a guardare il nostro presente come fosse un'immagine statica della realtà... beh il nostro futuro più prossimo non sarà altro che un'altra immagine statica da affiancare alla precedente, di secondo in secondo, un minuto dopo l'altro, in un'incessante erosione di quella che è la materia prima della nostra vita: il nostro tempo.",
                          "Questo susseguirsi di possibilità perse, di alternative mai provate, di versioni di noi stessi abortite ed inghiottite dalla trappola dell’inazione, costituisce l'eterno presente.",
                          "Il nostro futuro inizia a diventare possibile quando iniziamo ad immaginarlo.Ma come è già stato pensato e detto da menti più brillanti delle nostre, l'unica chance che la possibilità ha di istanziarsi nel presente è l'azione. Il nostro futuro inizia ad esistere quando agiamo per cambiare il nostro presente, per deviarlo dalla sua traiettoria precedente, per scardinarlo dalla fissità della ripetizione esausta di possibilità, per lanciarlo là dove gli unici riferimenti che ha sono ancora solo abbozzati da un'emozione, da una visione, da un'intuizione.",
                          "Se la scaturigine di ogni atto è una scelta, più o meno consapevole, più o meno razionale, questa può essere operata solo se prima viene pensata, sposata dal nostro io a livello emotivo ed ancor prima, deve poter essere immaginata.",
                          "Allora semplicemente...perché questo non accade? Cos'è che blocca il pensiero immaginifico? O al contrario, da dove si origina? Quale la scintilla che accende la fiamma?"
                      ]
                  },
                  {
                      title : 'Lo spazio rubato',
                      paragraphs : [
                          "Intanto, il pensiero deve poter essere pensato.Il che presuppone la presenza di uno spazio mentale, di un campo aperto in cui far correre le idee, le emozioni, l'immaginazione. Uno spazio mentale sgombro da tutto il resto, incurante di ogni conseguenza, semplicemente fine a sé stesso. Tale elemento è rappresentato dal contatto con l'insaturo. Si: il vuoto. Visto come assenza del suo opposto, il 'pieno'.Avete provato mai a muovervi in uno spazio pieno zeppo di cose? 'Impossibile, senza dello spazio libero', direte voi. E a buon ragione. Il concetto di 'vuoto' come spazio mentale non-pieno. Ci serve. Mai come in questa era - l’era della digitalizzazione - la nostra mente ne è assetata.",
                          "Alcuni riescono a trovarlo dentro loro stessi, nella pace della meditazione che annulla gli angusti confini del reale o nel mantra della preghiera, capace di far vibrare tutto il loro essere ad una frequenza diversa da quella della realtà circostante. Altri vi si imbattono per caso, perdendo lo sguardo nel cielo, magari assisi sotto un albero finché qualcosa (come una mela che cade loro in testa?) non li riporta al qui e adesso...oppure proiettando i propri pensieri come cavalli in corsa sulla sottile linea dell'orizzonte, là dove le nuvole sembrano posarsi sul mare calmo finché uno di essi non prende una forma diversa catturando un pezzo di razionalità (magari una formula per far avanzare la Fisica?).",
                          "Come in assenza di ossigeno mentale la fiamma dell'immaginazione non può ardere, così il pensiero strozzato dalla saturazione del nostro spazio mentale non può deflagrare, viene spento dalla costante pressione dei pensieri indotti dalla realtà circostante.",
                          "Tale spazio ci viene spesso rubato senza che neanche ce ne accorgiamo. “Come?” In mille modi.",
                          "Le teorie sociali sui GateKeepers ci hanno dimostrato che se qualcuno (magari esposto mediaticamente?) si arrabbia al posto nostro, fa sue le nostre ire, giura di combattere per noi le nostre battaglie, di curarsi lui dei nostri bisogni più pressanti per liberarci dal problema di farlo noi in prima persona... a quel punto non ci indigneremo più, non ci agiteremo più in risposta ad un bisogno non soddisfatto, rimarremo probabilmente lì fermi, catturati dal sollievo dell'immedesimazione, dalla promessa di un'azione salvifica che ci giunga da fuori.",
                          "Dove finisce allora la nostra istanza di cambiamento, la nostra partecipazione all'azione che deve nuovamente plasmare il nostro presente, che deve deviare le traiettorie delle nostre vite dalla sterile ripetizione? Dove finisce il nostro futuro? Nelle mani di altri. Esclusi una volta di più dallo spazio di partecipazione attiva in risposta alle chiamate dell'io, rimaniamo a guardare mentre il nostro futuro viene modellato dalle scelte degli 'intermediari del bisogno', i mezzani della perdita di contatto con noi stessi, i facilitatori dell’auto- tradimento delle nostre coscienze. Ogni giorno veniamo svuotati delle nostre pulsioni per vederle perennemente sviate - deviate dalle teorie del consumo - verso vacui palliativi. Senza nemmeno accorgercene, torniamo ad implodere nelle nostre gabbie mentali, inconsapevoli di ciò di cui veniamo quotidianamente defraudati.",
                          "La stessa cosa accade con l'immaginazione. Attratti da oggetti studiati per catturare il nostro sguardo, piacevoli al tocco, sempre pronti a semplificare tutto, a toglierci la fatica di pensare per risolvere anche i problemi più semplici, veniamo spinti dentro veri e propri fagocitatori dell'attenzione, centrifughe multi-sensoriali che condizionano le nostre reazioni, i nostri riflessi, la nostra capacità di ragionare, di teorizzare, di immaginare.",
                          "Se qualcuno ti immerge costantemente in una versione della realtà più appagante della tua vita reale, in una versione più precisa, più vivida, più estremizzata dei tuoi sogni... che bisogno avrai più di sognare liberamente? Perché tornare a risolvere i problemi della tua vita reale se puoi fuggire da essa con un tap o con un click? Se video-game sempre più realistici saziano costantemente la tua fame di fantasia, perché prendersi la briga di immaginare un mondo alternativo in cui realizzare tale fantasia?"
                      ]
                  },
                  {
                      title : 'La suadente schiavitù',
                      paragraphs : [
                          "La droga del nostro millennio è la costante assuefazione.",
                          "Tale droga fa 'avvizzire la nostra immaginazione; finché non diventa utile quanto un'appendice; fa in modo di colmare la nostra attenzione sempre e comunque. Se tutti quanti ci ritroviamo con l’immaginazione atrofizzata, nessuno costituirà mai una minaccia per il mondo.'",
                          "Il pensiero di massa, a-critico, modellato solo sul cieco, maniacale, compulsivo bisogno di soddisfazione immediata, di rimozione automatica di qualsiasi problema teorico/pratico che ci costringa a pensare, in nome della “facilità a tutti i costi” che vuole essere solo un altro modo per eludere la fatica di fermarsi a ragionare, di superare la momentanea frustrazione del fallimento, la necessità di sfuggire alle nostre coazioni a ripetere...",
                          "È tale miopia mentale, tale abbassamento di orizzonte a rendere possibile la suadente schiavitù della disattenzione, la manieristica e crepuscolare assenza di focus che ci ha resi ad un tratto incapaci di vedere il progresso nascere dall'analisi dell'errore, di abbracciare la fatica del superamento di un ostacolo tramite la ricerca, di osare pensare il pensiero non convenzionale, di vivere fuori dagli schemi.",
                          "Tutto questo ci lascia imprigionati in un costante stato di 'soddisfatta insoddisfazione' con la nostra capacità critica ingolfata, privata della forza dell'immaginazione, continuamente avvelenata da pacciame artatamente porzionato, calibrato sul costante contrasto di qualsiasi dubbio che possa increspare la patina della propaganda mediatica, artificialmente drogata ed irresistibilmente sexy. La nostra dose giornaliera, la pasticca per partecipare come indaffarati zombie al festino quotidiano della pornografia dell'opinione. Ogni giorno viene detto tutto ed il contrario di tutto. E lo reputiamo normale. La voce di quei pochi che provano ancora ad opporsi rischia di diventare un'eco sbiadita ed indistinguibile dal marasma mediatico.",
                          "Ecco perché il pensiero critico è importante e DEVE essere recuperato.",
                          "È la guardia all'ingresso delle nostre menti, l'arma che veglia sul nostro spazio mentale affinché non diventi una discarica dell'intelletto, per salvare la nostra capacità di entrare in contatto con l'insaturo in maniera sana, pulita, non inquinata.",
                          "È l'unico antidoto all'avvelenamento continuo della nostra capacità di focalizzare il pensiero in maniera costruttiva, l'unico argine all'inesausta manipolazione dei nostri bisogni che si perpetra quando perdiamo contatto da essi per accettare intermediari esterni più o meno subdoli.",
                          "Senza il pensiero critico diventiamo schiavi, marionette i cui fili sono manovrati da altri, senza nemmeno rendercene conto."
                      ]
                  },
                  {
                      title: 'Ogni fiamma ha la sua scintilla',
                      paragraphs : [
                          "Ora che ci è più chiaro come non possiamo sottrarci dal proteggere lo spazio in cui far brillare la nostra immaginazione, dobbiamo tornare per un attimo alla sua scaturigine, a come si genera la scintilla che porta la fiamma ad ardere.",
                          "Ogni scintilla che si rispetti nasce da una frizione, da uno sfrigolio, dal cozzare più o meno violento di una pietra focaia contro qualcosa capace di opporglisi, una dinamica di attrito.",
                          "L'immaginazione ha bisogno di idee preesistenti, già pensate da altri, strutturate, consumabili dalla nostra percezione sotto forma di informazione, di arte, di invenzione, etc. che rimandino a tale attrito, portandoci a scoprire percorsi mentali nuovi sospinti dalla voglia di immaginare. Dobbiamo poterle assorbire, sentirle nostre, in qualche modo averle studiate onde poterci sentire a nostro agio nel manipolarle in un modo che appartiene solo a noi. Per farle cozzare contro altri pensieri che ci soggiungono dal nostro incontro con l’insaturo, seguendo dinamiche inattese, che in quel momento non contempliamo appieno.",
                          "La scintilla che si genera da quell'incontro-scontro fra pensieri preesistenti e pensieri del tutto nuovi, spesso siamo soliti chiamarla 'intuizione', 'visione', 'creatività'. Ecco quindi che l'immaginazione si pone come moto irrefrenato di idee in movimento, sul tavoliere delle vastità concettuali dischiuse dal contatto con l'insaturo.",
                      ]
                  },
                  {
                      title : 'Un futuro che non può più attendere',
                      paragraphs : [
                          "Per trasformare dunque il nostro presente e renderlo in grado di realizzare il nostro futuro, servono idee, immaginazione, pensiero critico ed uno spazio mentale incontaminato, sgombro.",
                          "Anche le idee preesistenti, offerte dalla cultura del nostro tempo, servono allo scopo. Dobbiamo poterle consumare, ovvero nutrirci di esse e metabolizzarle, interiorizzarle, affinché proprio la nostra immaginazione possa gettare loro contro o incontro delle intuizioni.",
                          "E qui si affaccia un nuovo problema.",
                          "Come facciamo ad immaginare un futuro plausibile, attuabile, se gli elementi costituenti le origini di tale futuro non fanno parte del nostro orizzonte culturale? Come possiamo immaginarci a fare cose che oggi non facciamo, se ci mancano i mezzi concettuali per provare ad agire diversamente?",
                          "L'abbiamo visto: senza pietra focaia e ossigeno, niente scintilla, niente fiamma. Non possiamo dire con onestà di essere assetati di futuro, se poi al primo messaggio di errore che non conosciamo sul nostro smartphone ci fermiamo senza cercare di capire. Non possiamo continuare a subire il progresso senza diventarne parte. Che ci piaccia o no, qualcun altro lo sta plasmando in questo istante. Cosa faremo? Staremo fermi a guardare e ci faremo guidare, passivamente, trincerandoci dietro un qualunque: 'Perché impazzire a capirlo io? Tanto lo farà qualcosa o qualcun altro per me?' Il futuro non aspetterà, mentre noi tentenniamo nella fissità della nostra scomoda indecisione.",
                          "La maggior parte di tutto ciò che è stato teorizzato dai padri della bit-generation sull'avvento della Cibernetica, non solo si è già avverato (Internet, la realtà virtuale), ma in molti casi a livello tecnico è anche stato superato (avvento delle valute digitali, cryptocurrencies, decentralizzazione finanziaria e delle interconnessioni).",
                          "Altre cose predette dai padri visionari di quel movimento si stanno definendo ora, come evoluzione della società in risposta all'avvento di tali tecnologie, (crisi delle democrazie, crisi della globalizzazione, decadimento degli Stati Nazionali, nascita delle MegaCorporazioni). Altre ancora sono alle porte e - sulla scia degli strabilianti progressi della robotica d’avanguardia - premono per diventare mainstream (innesti biomeccanici, chip neurali, uso della biologia molecolare come media per lo stoccaggio di informazioni digitali).",
                          "L'interazione uomo-macchina è all'alba di una nuova era.",
                          "E noi? Resteremo in un angolo a guardare?",
                      ]
                  },
                  {
                      title : 'Un gap di cui prendere coscienza',
                      paragraphs : [
                          "Certo, anche noi ce ne rendiamo conto: l'idea di avere a che fare con computer che fanno tutto da soli o al posto nostro (Intelligenza Artificiale) può sembrare piacevole.",
                          "Fino ad un certo punto però. Ovvero fino a quando non arriveranno a toglierci il posto di lavoro, assorbito dall'automazione totale del processo cui prendevamo parte fino a ieri. Oppure fino a che non si porranno fra noi ed un nuovo datore di lavoro, come un muro invalicabile. Impedendoci persino di poter arrivare a fare un colloquio, perché il nostro Curriculum Vitae (posto che si usi ancora...) verrà scartato in automatico . Quel giorno forse ripenseremo a tutte le occasioni che abbiamo avuto, per affrontare quel buco di ignoranza nel quale ci eravamo comodamente adagiati come in un cul-de-sac.",
                          "Il problema è che quel giorno potrebbe essere ormai troppo tardi per recuperare il terreno perduto e potremmo dolorosamente scoprire che quel comodo conformismo dell’ignoranza si è trasformato nel frattempo in un’inequivocabile mancanza di possibilità. 'E perché? In fondo, meglio tardi che mai.' Starete pensando. Purtroppo o per fortuna, la velocità del progresso tecnologico non consente più stalli generazionali nel processo di apprendimento. Almeno non senza chiedere tributi altissimi con preoccupanti ripercussioni sociali. L'esperienza dei lock-down imposti dalla pandemia da COVID-19 ha reso questo aspetto molto tangibile. Chi viveva in zone di digital-divide o senza accesso ai mezzi materiali (know-how, disponibilità di dispositivi con determinati requisiti) è stato tagliato fuori per un certo lasso di tempo dalle dinamiche di apprendimento a distanza. Questo ha portato alcuni gruppi di persone a maturare un gap conoscitivo a cui dovranno metter mano in qualche modo, pena il rimanere indietro nel loro percorso di formazione di base.",
                          "Ecco, in scala ridotta abbiamo avuto un (non così) piccolo accenno al gap di fronte al quale la nostra intera società si trova a rincorrere, in una gara contro il tempo che per le fasce più vulnerabili della nostra società potrebbe rivelarsi spietata. Da un lato, i pochi - pochissimi se rapportati ai numeri rappresentativi della popolazione di un Paese - in grado di capire il progresso. In grado di farne parte attivamente, per guidarlo (posizioni apicali e ricercatori) o per integrarsi con esso (lavoratori dei vari settori che compongono il mondo Cyber). Dall'altro, la sempre più vasta platea di chi può solo subire l'avanzata delle tecnologie digitali, perché non ha i mezzi concettuali in primis e materiali in subordine per poter vivere il progresso in maniera consapevole e quindi attiva.",
                          "Immaginatevi di fronte ad un'estremizzazione quale: ”Preferireste imparare a programmare o essere programmati?” Cosa rispondereste?"
                      ]
                  },
                  {
                      title : 'L’uscita dai labirinti della paranoia',
                      paragraphs : [
                          "'Ok. Ma cosa c'entra tutto questo con l'immaginazione? E come possiamo evitare di venire inghiottiti da questo gap culturale?' Quello a cui stiamo pensando è una tipologia diversa di evangelizzazione digitale.",
                          "Non una fatta di computer e complessi sistemi informatici che si spieghino da sé. Se ci trovassimo di fronte ad una sedia che, animandosi, ci salutasse con un: 'Ciao! Sono una sedia. Ti va di sederti?' ...ne sapremmo esattamente quanto prima circa la sua natura e la sua funzione. A meno di non accettarne l’invito ad accomodarci sopra di essa, fatto che porta con sé una conseguenza non trascurabile: avremmo fatto ciò che quell’oggetto ci ha invitati a fare senza nemmeno capirne la provenienza e le finalità. Per capire davvero l’interazione è necessario un punto di vista esterno. Forse messo a disposizione da chi quella sedia-che-parla l’ha prima ideata e poi realizzata, oppure da chi ci si è seduto sopra prima di noi.",
                          "'Ma...allora volete farci diventare paranoici? Mica possiamo passare la vita in piedi!' No. Avete assolutamente ragione. Non si può.",
                          "Al contrario: vogliamo cercare di staccarvi di dosso quell’appiccicoso torpore dell’intelletto che rende ignava la vostra curiosità circa la sedia-che-parla, affinché possiate osservarla con occhi nuovi. Arrivando a capire, senza paure o claustrofobiche ansie da mancanza di know-how, cosa avete di fronte, a cosa serve, perché fa ciò che fa (o promette di fare).",
                          "Senza nutrire un pensiero paranoico - che si alimenta di paure - bensì esercitandone uno critico - che si sviluppa dal vaglio di elementi oggettivi.",
                          "D’altro canto,'ragionare costa fatica'. Il semplice fatto di proporlo sembra essere spesso contro-corrente e parecchio discorde rispetto alla promessa di “facilità ad ogni costo”, incarnata dai prodotti della cultura dell’intermediazione tecnologica dei bisogni. Proprio perché si parla di 'costo' ve ne è uno implicito anche nel somministrarsi la droga della facilità-senza-ragionamento giorno dopo giorno. Tale prezzo, che finiamo più o meno consapevolmente per pagare è il graduale avvizzimento ed infine la morte del pensiero critico. Ovvero il prodromo della schiavitù.",
                      ]
                  },
                  {
                      title : 'Una learning-suasion per abbracciare il futuro',
                      paragraphs : [
                          "Nessun dubbio che proviate la sgradevole sensazione di trovarvi di fronte ad una barriera che percepite come invalicabile. In effetti, siamo qui proprio per questo: per farci delle domande e provare a dare delle risposte a riguardo, proponendo una via d’uscita.",
                          "Come fare dunque per rimuovere tale barriera? Dobbiamo per l’appunto cambiare quella percezione: la mancanza di sapere NON è una barriera invalicabile. Tale percezione è indotta. Come è indotto associare un pensiero di 'fatica' all’atto dell’apprendimento. E se al posto di bollare come “faticoso” tale processo, fossimo portati a percepirlo come piacevole? Magari persino divertente o interessante?",
                          "'Interesse', questo è il punto focale! L’interesse è l’elemento propulsore del processo di comprensione, che è quello che ci dota degli strumenti utili ad esercitare il pensiero critico. Ecco quindi cosa dobbiamo fare: rimboccarci le maniche, alzare il cofano ed aiutare a far ripartire questa meravigliosa meccanica nella testa delle persone. Dobbiamo rendere interessante e culturalmente commestibile quello che fino ad oggi è stato tenuto a distanza ed etichettato come 'troppo tecnico', 'difficile da capire', 'oscuro' e 'noioso'; proprio perché a volte, ahimè, lo è davvero. Che l’interesse generato dal piacevole incontro fra nozione tecnica e fantasia, diventi una learning-suasion con gli stessi caratteri di appartenenza dei grandi movimenti culturali che hanno segnato il passaggio fra ere tecnologiche diverse.",
                          "Dobbiamo darci da fare per creare una cultura Cyber e affinché questa diventi mainstream, parte della quotidianità, di un universo mentale quanto più condiviso, come tratto distintivo dell’era in cui chi verrà dopo di noi potrà riconoscere “il momento in cui abbracciammo il futuro”.",
                      ]
                  },
                  {
                      title : "Forme arcaiche, contenuti moderni. Homo digitalis.",
                      paragraphs : [
                          "'Meraviglioso. Ma...all’atto pratico?' A volte un approccio semplice a problemi complessi si rivela essere una mossa vincente.",
                          "Per esempio, come facevano i nostri nonni a renderci meno amara una medicina dal sapore difficile da accogliere? Ci aiutavano a mandarla giù sminuzzandola in mezzo alla nostra pietanza preferita, oppure la addolcivano dandoci un pò di zucchero. Allo stesso modo, vogliamo provare a descrivere le varie sfaccettature del mondo Cyber utilizzando un punto di vista diverso, cioè mischiandole con elementi narrativi della vita normale o che potrebbe diventare verosimilmente normale fra qualche anno. Non quindi un futuro remoto, del quale i più non sarebbero capaci di rinvenire le origini nell'attuale presente. Bensì un presente o un futuro prossimo del tutto plausibili.",
                          "Quale contenitore utilizzare per questo messaggio? Per quanto possa apparire vetusto, forse persino arcaico, il libro ancor oggi rappresenta un potente mezzo di diffusione del sapere. Quel susseguirsi di caratteri scritti ci obbliga a leggere, a riflettere, a ripetere dentro le nostre menti enunciazioni di concetti che finiamo per idealizzare, per figurare, per immaginare.",
                          "Una volta di più vogliamo affidare il nostro messaggio al potere evocativo della parola, del racconto, della storia narrata. Poco importa che sia un messaggio di modernità, alternativo rispetto al presente in cui viviamo, oppure di verosimile somiglianza con esso. A noi basta che la fantasia di una trama avvincente, unita a delle spiegazioni a portata di tutti, compia il miracolo nella testa del lettore. Ovvero quello di prenderne per mano l'immaginazione, di portarla a sgranchirsi le gambe per un pò, giusto il tempo necessario a risvegliare un interesse, una curiosità. Con la speranza che questa possa diventare voglia di capire, di apprendere, di informarsi anche quando l'ultimo capitolo porterà gli occhi a scorrere sulla parola 'Fine'.",
                          "Per questo abbiamo scelto il nome un pò naïf di 'Duchi dell'Immaginazione'. Non vogliamo prostrare il lettore con la lettura di oscuri manuali o lunghe liste di incomprensibili istruzioni. Al contrario, vorremmo far leggere per immaginare; per aiutare il lettore a concepire a sua volta modernità, cyber, futuro. Per riprendere pian piano possesso degli elementi necessari ad orientarsi autonomamente, nella ricerca della propria 'pietra focaia'. Affinché ognuno di noi possa accendere una scintilla tutta sua, illuminando il futuro proprio e - perché no - magari anche quello degli altri. Affinché sia sempre l’uomo a programmare la macchina e mai la macchina a comandare la mente dell’uomo.",
                          "E’ compito della nostra generazione fare in modo che dall’era della digital transformation si possa generare un Rinascimento Digitale (Digital Renaissance) per un futuro che potrà essere migliore del nostro presente solo se sapremo immaginarlo come tale.",
                          "Il futuro è adesso.",
                          "Benvenuti."
                      ]
                  }
              ],
              currentIndex : 0
          }
      },
      methods:{
         /**
         *  @description sets current index to new indez
         *  @param {int} newIndex
         */
          setCurrentIndex(newIndex){
              setTimeout(()=>{
                  this.currentIndex = newIndex
              }, 500)
          }
      }
  }

</script>

<style lang="sass" scoped>

  li
      padding: 0.5rem  2rem
      text-decoration: underline
  h1
      font-family: daniel
  .paragraphs-container
      max-height: 50vh
      overflow: auto
      //custom navbar
      &::-webkit-scrollbar
          width: 10px
      /* Handle */
      &::-webkit-scrollbar-thumb
          background: gold
          border-radius: 30px
      /* Handle on hover */
      &::-webkit-scrollbar-thumb:hover
          background: #555
  #text-section
      z-index: 1
  #sidenav
      z-index: 99
</style>
