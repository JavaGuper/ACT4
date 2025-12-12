🎤 Voice Commander: Interfície de Control per Veu (PoC)
🌟 Títol i Descripció Breu del Projecte
Voice Commander és una Prova de Concepte (PoC) d'una aplicació d'escriptori desenvolupada amb Electron i Vue 3 que permet la interacció natural mitjançant la veu. Aquesta aplicació utilitza la Web Speech API nativa per capturar i interpretar ordres de veu en català, demostrant com es pot integrar un sistema de control de veu complet amb gestió d'estats, comandes simples i control de l'aparença de la interfície.
L'objectiu principal és provar la viabilitat de les interfícies d'usuari de veu (VUI) en entorns d'escriptori.
🛠️ Tecnologies Utilitzades
Categoria
Tecnologia
Versió
Descripció
Plataforma
Electron
latest
Framework per crear l'aplicació d'escriptori.
Frontend
Vue 3 (Composition API)
latest
Framework UI reactiu per a la interfície.
Estil / UI
Vuetify 3
latest
Llibreria de components Material Design.
Veu
Web Speech API
N/A
API nativa del navegador Chromium per al Reconeixement de Veu.
Lògica
Vue Composables
N/A
Lògica de reconeixement encapsulada en useSpeechRecognition.js.

⚙️ Instruccions d'Instal·lació i Execució
Per posar en marxa i executar el projecte en un entorn local de desenvolupament:
Prerequisits
Node.js (recomanada la versió LTS)
npm (Node Package Manager) o yarn
Pas 1: Clonar el Repositori
git clone [URL_DEL_REPOSITORI]
cd voice-commander-project


Pas 2: Instal·lar Dependències
Instal·la totes les dependències del projecte:
npm install 
# o 
yarn install


Pas 3: Executar l'Aplicació en Mode de Desenvolupament
Inicia l'aplicació d'escriptori Electron en mode de desenvolupament, amb hot-reload:
npm run electron:serve
# o
yarn electron:serve


Permisos de Micròfon: L'aplicació principal d'Electron (main.js o background.js) està configurada per acceptar automàticament el permís media del micròfon, evitant diàlegs de seguretat a l'inici.
🎙️ Descripció de l'Ús Bàsic de l'Aplicació
L'aplicació es controla principalment mitjançant un botó central que activa el micròfon i una sèrie de comandes de veu predefinides (en català).
1. Inici i Estats
Activació: Prem el botó [Escolta] al centre de la pantalla. L'aplicació canviarà a l'estat Escoltant... i la icona del micròfon començarà a polsar (animació animate-pulse).
Resultats Intermedis: Mentre parles, el text que el navegador està detectant (però encara no ha finalitzat) apareixerà sota l'estat com a "Detectant: [text intermig]".
Resultat Final: Quan deixes de parlar, el reconeixement finalitza, s'executa la comanda detectada i es mostra el missatge de feedback.
2. Comandes de Veu Suportades
L'aplicació reacciona a les següents frases clau (la coincidència no és sensible a majúscules ni accents en la lògica de reconeixement):
Frase Clau
Acció de l'Aplicació
Feedback Visual
"Saluda"
Mostra un missatge de benvinguda i una alerta (per a demostració).
Targeta de color Verd (success).
"Ajuda"
Mostra un missatge informatiu sobre la PoC.
Targeta de color Blau (info).
"Esborra" / "Borrar"
Reseteja la interfície al missatge inicial ("En espera").
Targeta torna al color Gris/Primari (primary).
"Mode fosc"
Canvia el tema de l'aplicació a mode fosc (dark).
Missatge de confirmació.
"Mode clar"
Canvia el tema de l'aplicació a mode clar (light).
Missatge de confirmació.
Qualsevol Altra Frase
Si no coincideix amb cap comanda coneguda.
Snackbar (vermell) a la part inferior amb la frase no reconeguda i targeta Taronja (warning).


