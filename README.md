# Informe Tècnic de Planificació, Adequació i Muntatge d'un Ordinador Clònic amb Maquinari Reutilitzat

> Informe tècnic sobre el disseny, adequació, muntatge i verificació d'un ordinador clònic a partir de components reutilitzats.

## 1. Introducció i Criteri de Selecció Lògica dels Components

El present informe detalla el procediment tècnic per al disseny, adequació i construcció d'un ordinador clònic a partir de components informàtics en desús o reciclats. En l'àmbit dels sistemes microinformàtics, l'èxit d'un muntatge d'aquestes característiques rau en una planificació estricte basada en la jerarquia de dependències del maquinari.

No es tracta d'aconseguir peces de manera aleatòria, sinó de seguir un ordre coherent de compatibilitat que s'inicia sempre amb l'elecció conjunta del processador i la placa base. Aquests dos elements actuen com el nucli del sistema i dictaminen de forma immutable quina tipologia de memòria RAM, quines dimensions de xassís i quina potència elèctrica es requeriran posteriorment en les fases successives del projecte.

En aquest projecte en concret, la columna vertebral de l'equip s'ha definit mitjançant una placa base Gigabyte GA-A320M-S2H amb un processador AMD integrat sobre un sòcol Socket AM4.

A partir d'aquesta base, s'ha fet una prospecció lògica dels components secundaris. Com que es va determinar que el processador disposava d'una unitat de gràfics integrats (APU), es va poder simplificar el pressupost energètic i d'espai al prescindir d'una targeta gràfica dedicada pesant. Això va permetre certificar la compatibilitat d'una font d'alimentació Unyka de 300W reals, una potència que seria insuficient per a un equip de jocs d'alt consum, però que resulta ideal i molt relaxada per a aquest laboratori, on el consum estimat global no superarà els 125W a màxima càrrega.

Seguint aquest mateix fil de compatibilitat dictat per la placa, s'ha triat un mòdul de memòria Crucial DDR4 de 4GB a 2400 MHz.

Pel que fa a l'emmagatzematge, es va optar per un esquema híbrid molt eficient: un disc de tecnologia sòlida SSD Kingston de 240 GB per a allotjar el sistema operatiu i un disc mecànic HDD Seagate Barracuda de 750 GB de 3.5 polzades per a dades massives.

Finalment, es va incorporar una unitat òptica de DVD Hitachi-LG i un xassís de format Semiescriptori (Mid-Tower) de la signatura GDX System que, un cop analitzat l'espai intern, va resultar totalment compatible amb les mides Micro-ATX de la placa i les dimensions de les unitats de disc.

## 2. Preparació de l'Espai Físic, Eines i Seguretat de Taller

Abans de manipular qualsevol component electrònic, cal adequar l'espai físic del laboratori sota estrictes criteris professionals per mitigar el risc de descàrregues electrostàtiques (ESD), que podrien danyar de forma irreversible els semiconductors de la placa base o de la memòria. L'espai triat ha de ser una superfície completament neta, seca i no conductora, utilitzant preferiblement una estoreta de silicona o cautxú antiestàtic com a base de treball. La il·luminació ha de ser directa i potent per permetre la lectura de la serigrafia microscòpica dels circuits impresos.

Com a mesura de seguretat fonamental, la font d'alimentació i qualsevol eina elèctrica han de romandre completament desconnectades de la xarxa elèctrica general durant les fases de preparació.

Pel que fa a l'utillatge, es prepara un joc de tornavisos de precisió amb punta d'estrella o cruciforme de mida PH2, que és l'estàndard per a la cargolaria informàtica general. Com a consumibles tècnics d'adequació, es disposa d'un pot d'alcohol isopropílic com a mínim del 90%, el qual té la propietat d'evaporar-se instantàniament sense deixar cap mena de residu humit conductor. També es preparen draps de microfibra o mocadors de cel·lulosa que no desprenguin borrissol, un pinzell de truges suaus i sintètiques per a desplaçar la pols, i un tub de pasta tèrmica nova d'alta conductivitat tèrmica per a la correcta transmissió de calor del processador.

<p align="center">
  <img src="Foto 1 L'espai de treball.jpg" alt="L'espai de treball" width="45%">
  <img src="img/02_seguridad_esd.jpg" alt="Seguretat ESD" width="45%">
</p>

## 3. Protocol de Neteja i Manteniment Preventiu dels Components

Els components que provenen d'equips en desús acostumen a acumular pols ambiental i greixos que actuen com un aïllant tèrmic o que, en cas d'humitat, podrien provocar curtcircuits en les pistes. Per aquest motiu, el segon bloc del protocol exigeix un sanejament exhaustiu element per element abans de realitzar cap mena de connexió o prova elèctrica.

El procés s'inicia amb el bloc del processador i la placa base. Sense retirar la CPU del seu sòcol per protegir els delicats pins inferiors d'AM4, s'humiteja un drap de microfibra amb alcohol isopropílic i es frega suaument la superfície superior metàl·lica (l'IHS) del processador. Aquesta acció es repeteix fins a eliminar qualsevol resta de la pasta tèrmica grisa i resseca original, deixant el metall polit i permetent la lectura neta del model de la CPU gravat amb làser. Paral·lelament, es passa el pinzell antiestàtic per les ranures on es punxa la memòria RAM i pels ports d'expansió PCIe per assegurar que cap partícula de pols obstrueixi els contactes daurats.

El següent element crític s'identifica com el sistema de refrigeració, compost pel ventilador elèctric Foxconn i el radiador de làmines d'alumini d'AMD.

Es separen ambdues peces desmuntant els clips plàstics.

Les aspes del ventilador es netegen una a una amb un bastonet de cotó impregnat en alcohol isopropílic per eliminar la pols adherida que afegeix pes de desequilibri a l'eix. El bloc metàl·lic d'alumini es bufa com a primera mesura amb aire comprimit o es renta per eliminar la brutícia dels canals interns; en cas de rentar-lo, s'ha de garantir un assecat absolut abans de tornar-lo a ajuntar amb el motor elèctric. Finalment, es netegen els connectors de dades i potència SATA de l'SSD, l'HDD i el lector de DVD amb un pas ràpid d'alcohol isopropílic per minimitzar la resistència elèctrica en el bus de comunicació.

**4. Protocol de Verificació Prèvia i Prova a l'Aire (POST Extern)**

Atès que s'està treballant amb components de reciclatge l'historial operatiu dels quals és completament desconegut, s'estableix com a pas obligatori en el protocol la realització d'una prova a l'aire o d'arrencada externa. L'objectiu d'aquesta actuació és verificar que el nucli bàsic del sistema (placa base, processador, memòria RAM i font d'alimentació) és capaç de superar amb èxit el procés POST (Power-On Self-Test) i emetre senyal de vídeo abans d'invertir temps i esforç en la integració mecànica definitiva dins del xassís. En cas d'existir algun component defectuós, aquest mètode estalvia hores de taller en permetre un diagnòstic i un intercanvi de peces immediat.

El procediment d'assaig s'executa col·locant la placa base Gigabyte de manera totalment horitzontal sobre una superfície aïllant, utilitzant com a banc de proves la seva pròpia caixa de cartró de fàbrica. S'evita estrictament l'ús de la bossa antiestàtica a l'exterior com a base, ja que la seva pel·lícula externa pot ser lleugerament conductora.

A continuació, es realitza el muntatge dels components mínims per al POST:

S'insereix el mòdul de memòria RAM Crucial al primer slot, s'aplica una petita quantitat de pasta tèrmica nova (de la mida d'un pèsol) al centre de la CPU i es fixa el conjunt del dissipador d'alumini connectant el ventilador Foxconn al port CPU_FAN.

Tot seguit, es disposa la font d'alimentació Unyka al costat de la placa i es connecten exclusivament els dos cables d'energia vitals per a la placa: el connector ATX de 24 pins i el cable d'alimentació suplementari de la CPU de 4 pins (ATX 12V). Es connecta un monitor a la sortida HDMI de la placa base i s'endolla la font a la xarxa elèctrica, col·locant el seu interruptor posterior en posició I.

Com que en aquesta fase no es disposa del botó físic de la caixa per engegar el sistema, s'aplica una tècnica estàndard de laboratori de microinformàtica: utilitzant la punta d'un tornavís d'estrella net, es realitza un pont elèctric momentani (un curtcircuit controlat d'un segon) tocant simultàniament els dos pins de coure retolats com a PW+ i PW- (Power Switch) en el panell frontal de la placa base. Això replica exactament el pols de tancament de circuit que faria el botó de la torre.

En rebre el pols, es verifica de forma immediata que el ventilador de la CPU comença a girar sense obstruccions i, després d'uns segons de comprovació interna del xipset A320, el monitor s'encén i mostra la pantalla de la UEFI/BIOS de Gigabyte. Aquesta confirmació visual és la garantia tècnica que el nucli de control funciona correctament.

En acabar la comprovació, es torna a fer un pont curt als mateixos pins per apagar el sistema, es desconnecta la font del corrent elèctric i es dóna llum verda de compatibilitat elèctrica per al conjunt base.

## 5. Protocol Professional d'Auditoria, Backup i Sanitització en Estació de Servei

Mentre el nucli base del clònic està certificat en el banc de proves, s'activa de forma paral·lela el protocol de tractament de les unitats d'emmagatzematge.

Atès que l'SSD Kingston de 2.5" i l'HDD Seagate de 3.5" procedeixen d'equips externs en desús, la metodologia professional desaconsella connectar-los directament al PC en construcció sense abans haver-ne analitzat la seguretat i la integritat. Existeix un risc real de transmissió de malware resident o infecció a nivell de sector d'arrencada. Per aquest motiu, es traslladen ambdues unitats a una estació de treball o ordinador auxiliar de taller ja operatiu i protegit.

La connexió a l'ordinador de taller es realitza mitjançant ports SATA de recanvi configurats en mode hot-swap, o mitjançant adaptadors i badies externes de tipus Docking Station connectades via USB 3.0 / USB-C. Un cop les unitats són detectades per l'estació del taller, s'executa un complet procediment estructurat gràcies al següent ecosistema d'eines de programari professional:

Auditoria de Contingut i Desplaçament de Seguretat (Backup): S'examinen les estructures de fitxers i els directoris heretats que encara conserven els discos per salvaguardar informació crítica de l'anterior cicle de vida.

Eines utilitzades: CrystalDiskInfo (per a una lectura ràpida de l'estat general "Bo/Risc/Dolent" de la telemetria) i GSmartControl o HD Tune Pro (per realitzar tests d'autocomprovació estesos —Extended Self-Test— que analitzen físicament la superfície de l'HDD Seagate a la recerca de sectors defectuosos o l'estat d'estrés de les cel·les NAND del SSD Kingston).

Esborrat Seguro i Formatat de Baix Nivell (Sanitització): Es destrueix qualsevol estructura de dades prèvia o codi maliciós allotjat en el codi d'arrencada.

Eines utilitzades: Eina de Gestió de Discos de Windows / Diskpart (per fer neteges estructurals de capçaleres mitjançant la comanda clean) o GParted (en entorns Linux de taller per eliminar per complet antigues taules de particions MBR o GPT). Finalment, s'aplica l'eina HDD Low Level Format Tool en cas de requerir un esborrat sector per sector, definint posteriorment l'SSD Kingston com a "espai sense assignar" (net per a l'instal·lador) i l'HDD Seagate com una unitat buida sota el sistema de fitxers NTFS o ext4.

Un cop finalitzat aquest procés, es desmunten de forma segura els discos de l'ordinador de taller i es preparen, totalment nets de dades i de programari maliciós, per a la fase d'integració física.

## 6. Procediment de Muntatge Definitiu al Chassis Pas a Pas

Un cop validat el nucli i els discos durs han estat correctament tractats i formatats a l'estació de servei, es procedeix a la integració mecànica de tots els elements dins de la caixa GDX System.

Fase A: Preparació i Fixació de la Placa al Chassis

El treball es desplaça ara cap a l'interior de la caixa. El premier pas és agafar la xapa metàl·lica dels ports (I/O Shield) i encaixer-la a pressió a la ranura rectangular del darrere de la caixa, empenyent des de dins cap a fora.

Després, es verifica la disposició dels separadors de rosca metàl·lics (daurats) sobre la paret interna del xassís; se seleccionen i es col·loquen exclusivament en aquells forats que corresponguin al format de mida Micro-ATX d'aquesta placa de Gigabyte per evitar que el circuit imprès toqui directament la xapa de la torre i provoqui un curtcircuit elèctric.

Un cop llestos els separadors, s'introdueix la placa base (que manté la CPU, la RAM i el dissipador instal·lats) de forma lleugerament inclinada, fent coincidir tots els connectors de sortida del darrere amb els forats de l'I/O Shield.

Quan la placa assenta perfectament alineada sobre els separadors daurats, es fixen els cargols de rosca fina alternant el collat en forma de creu per evitar tensions mecàniques locals en el circuit de la placa.

Tot seguit, s'instal·la la font d'alimentació Unyka a la part superior esquerra del xassís, fixant-la fermament des del darrere exterior de la caixa amb quatre cargols hexagonals de rosca gruixuda.

Fase B: Integració de Discos, Unitat Òptica i Frontal

Amb el nucli elèctric fixat, es passa a la integració dels sistemes d'emmagatzematge prèviament formatats.

Per a poder instal·lar el lector de DVD Hitachi-LG, primer s'ha d'agafar el frontal de plàstic que es va desmuntar i fer pressió sobre les pestanyes de la tapa superior de 5.25 polzades per extreure-la, creant així la finestra física per a la safata.

Després, s'introdueix la unitat de DVD des de la part exterior frontal cap endins a través de les guies metàl·liques superiors de la caixa i es fixa amb dos cargols de rosca fina a cada lateral del xassís.

Seguidament, s'agafa el disc mecànic HDD Seagate de 3.5 polzades i es col·loca dins la gàbia metàl·lica de la secció intermèdia, orientant els seus connectors cap a l'interior (mirant cap a la placa base) i fixant-lo amb cargols de rosca gruixuda. L'SSD Kingston de 240 GB de 2.5 polzades es disposa collat directament sobre els encunys específics que aquest xassís porta habilitats a la seva base interna o a la paret de xapa vertical.

Un cop col·locades les dues unitats, es torna a encaixar a pressió el frontal de plàstic a l'estructura de la torre.

Fase C: Connexió del Cablejat i Panell Frontal

La darrera fase del muntatge consisteix a connectar el mapa de cables per donar energia i comunicació final al sistema:

En primer lloc, es realitzen les connexions d'alimentació principal que surten de la font Unyka: el connector gran de 24 pins ATX es connecta al port lateral dret de la placa, i el cable d'alimentació ATX 12V de 4 pins es connecta a la cantonada superior esquerra de la placa base per alimentar les fases de la CPU.

Després, es distribueix la línia de cables de corrent SATA de la font, connectant-los en cascada de dalt a baix al lector de DVD, a l'HDD Seagate i a l'SSD Kingston.

Per a la transmissió de dades, es connecten tres cables de bus SATA independents des d'aquestes unitats fins als ports numerats SATA3 0, 1 i 2 de la placa base.

Per acabar, es connecta la trena de cables de control que prové del frontal de la caixa.

El cable de l'àudio integrat (HD AUDIO) es connecta al port F_AUDIO situat a la cantonada inferior esquerra de la placa.

Els cables de comunicació USB es punxen al port de pins F_USB1.

Finalment, els pins ultra prims del tauler de control (F_PANEL) es distribueixen minuciosament a la cantonada inferior dreta: el cable del botó d'encesa (POWER SW) es col·loca als pins del fons superiors, el botó de reinici (RESET SW) a la fila inferior dreta, i es connecten els indicadors LED (HDD LED i POWER LED) respectant la polaritat de manera que el cable de color (positiu) quedi fixat al pin esquerre indicat en la serigrafia de la placa.

## 7. Control de Qualitat Final i Posada en Marxa de l'Equip

Un cop completat el muntatge físic interior, es realitza una inspecció visual final d'assegurament de la qualitat abans de tancar les tapes i subministrar energia elèctrica definitiva. Es verifica que cap cable de la font d'alimentació hagi quedat en una posició tensa o que pugui obstruir o fregar les aspes del ventilador de la CPU o del propi extractor de la font.

Es tanca el xassís, es connecta el cable d'alimentació de corrent altern a la part posterior de la font Unyka i es commuta el seu interruptor a la posició d'encesa I.

Es connecta un monitor directament a la sortida de vídeo digital HDMI o analògica VGA del panell posterior de la placa base Gigabyte per poder rebre el senyal directe de la unitat gràfica integrada de l'APU AMD.

En prémer el botó d'encesa del panell frontal de la caixa, l'equip executa el procés POST a nivell de maquinari complet.

Mitjançant la pulsació de la tecla Suprimir o F2, s'accedeix a la pantalla de configuració de la UEFI/BIOS. En aquest entorn de diagnòstic, es valida finalment que el sistema reconeix el model de processador AMD, que llegeix la capacitat de 4GB de la memòria RAM Crucial corrent a la seva freqüència nominal de 2400 MHz, que les temperatures de la CPU es mantenen estables dins dels marges de seguretat en repòs i que el bus SATA llista correctament les tres unitats d'emmagatzematge integrades, netes i prèviament buidades a l'ordinador de taller.

El sistema clònic es dóna per finalitzat i certificat amb èxit, restant a punt per a rebre la instal·lació neta del sistema operatiu mitjançant un llapis de memòria USB d'arrencada.

## 8. Conclusions, Funcionalitat Target i Proposta de Millores de Rendiment

### 8.1. Funcionalitat i Àmbit d'Aplicació de l'Equip Recondicionat

Un cop certificat el correcte funcionament del maquinari, es determina que aquest ordinador clònic té una viabilitat operativa excel·lent orientada a tres àmbits funcionals molt concrets.

En primer lloc, com a estació de treball per a ofimàtica bàsica i navegació web, on la presència de l'SSD Kingston garantirà una agilitat de resposta immediata en la càrrega de programari d'edició de textos i gestió de correu electrònic.

En segon lloc, és un equip ideal per actuar com a servidor domèstic de baixa potència (Home Server) o dispositiu NAS (Network Attached Storage), aprofitant els 750 GB de l'HDD Seagate net per a l'emmagatzematge de fitxers en xarxa local, còpies de seguretat o serveis de xarxa lleugers.

Finalment, serveix com a laboratori físic de proves per al desplegament de sistemes operatius o administració de serveis de xarxa basats en línia de comandes (CLI).

A causa de la limitació estricta dels 4 GB de memòria RAM actuals, es descarta l'ús de sistemes operatius moderns amb entorns gràfics feixucs, com ara Windows 11.

Per a aquesta configuració base, es recomana la instal·lació d'una distribució de Linux de llarga durada (LTS) orientada a servidors o amb escriptoris lleugers (com Ubuntu Server, Debian o Linux Mint XFCE), o bé una versió optimitzada de Windows orientada a l'estabilitat i al baix consum de recursos, com Windows 10 IoT Enterprise LTSC.

### 8.2. Proposta Escalonada de Millores per a un Major Rendiment

Per tal d'ampliar el cicle de vida d'aquest ordinador clònic i permetre tasques lligades a la virtualització (com Docker o micro-màquines virtuals) o fins i tot jocs bàsics, el sòcol AM4 obre la porta a una ruta de millora altament eficient i econòmica:

Ampliació de la Memòria RAM i Activació del Dual Channel (Prioritat Màxima): Consisteix a expandir el sistema fins a un kit de 2x8 GB (16 GB) DDR4 a 3200 MHz. Atès que l'APU reserva part de la RAM com a memòria de vídeo (VRAM), passar a 16 GB evitarà l'estrangulament de dades.

Addicionalment, l'activació del Dual Channel duplicarà l'amplada de banda del bus (de 64 a 128 bits), incrementant fins al 40% el rendiment dels gràfics integrats.

Migració de l'Emmagatzematge Principal a NVMe M.2: La placa base Gigabyte disposa d'un port dedicat M.2 NVMe PCIe Gen3 x4.

Substituir l'SSD SATA de 2.5" per un disc SSD M.2 NVMe d'1 TB (com un Kingston NV2 o similar) permetria passar d'una velocitat de lectura de 500 MB/s a més de 3.000 MB/s, eliminant qualsevol coll d'ampolla en la transferència de fitxers grans.

Actualització del Processador a Generacions Superiors: El xipset AMD A320 d'aquesta placa és compatible, prèvia actualització de la BIOS, amb els processadors Ryzen de les sèries 4000 i 5000. Adquirir en el mercat de segona mà un Ryzen 5 4600G o Ryzen 5 5600G dotaria l'equip de 6 nuclis i 12 fils amb gràfics Radeon Vega molt més potents.

El consum elèctric d'aquestes CPU es mantindria dins dels 65W, respectant amb total seguretat els marges de la font Unyka de 300W.
