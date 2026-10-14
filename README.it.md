<div align="center">

<a href="https://ncpack.roca.software/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/banner-dark-it.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/banner-light-it.svg">
    <img alt="NCPack Studio: video leggeri la metà. Qualità misurata, non promessa." src="docs/banner-dark-it.svg" width="100%">
  </picture>
</a>

<br>

[![Prova gratuita di 7 giorni](https://img.shields.io/badge/Prova_gratuita-7_giorni-d7f24c?style=for-the-badge&labelColor=151a02)](https://ncpack.roca.software/#demo)
[![macOS](https://img.shields.io/badge/macOS-12%2B_·_Apple_silicon-f2f4ef?style=for-the-badge&logo=apple&logoColor=151a02&labelColor=d7f24c)](https://ncpack.roca.software/)
[![Windows](https://img.shields.io/badge/Windows-64_bit-f2f4ef?style=for-the-badge&logo=windows&logoColor=151a02&labelColor=d7f24c)](https://ncpack.roca.software/)

**[Sito](https://ncpack.roca.software/)** · **[Prova gratuita](https://ncpack.roca.software/#demo)** · **[Prezzi](https://ncpack.roca.software/#prezzi)** · **[Benchmark](BENCHMARKS.md)** · **[Segnala un problema](../../issues/new/choose)** · **[🇬🇧 English](README.md)**

</div>

<br>

NCPack Studio è un'app per computer che comprime i video in **AV1** e misura la qualità di **ogni
fotogramma** del file finito con [VMAF](https://github.com/Netflix/vmaf), la misura sviluppata da Netflix.
Se un video non può diventare più leggero senza perdere qualità, resta com'è: **non ricevi mai un file più pesante.**

<div align="center">
  <img src="docs/images/app-demo.webp" alt="NCPack Studio al lavoro: un video viene trascinato, stimato e compresso a 33,3 MB con VMAF 96,65" width="860">
  <br><sub>Trascini un video, vedi il peso prima di cominciare, ricevi un file verificato fotogramma per fotogramma.</sub>
</div>

<br>

## ✦ In breve

<table>
  <tr>
    <td align="center" width="25%"><h1>−59,5%</h1><sub><b>Video Full HD da telefono</b><br>82,2 → 33,3 MB · VMAF 96,65</sub></td>
    <td align="center" width="25%"><h1>−71,8%</h1><sub><b>Corso SCORM</b><br>46,9 → 13,3 MB · funziona sulla piattaforma</sub></td>
    <td align="center" width="25%"><h1>2,6%</h1><sub><b>Errore mediano</b><br>della stima del peso, 14 video reali</sub></td>
    <td align="center" width="25%"><h1>0 su 15</h1><sub><b>File più pesanti</b><br>dell'originale, nei nostri test</sub></td>
  </tr>
</table>

<sub>Misure al livello Alta (VMAF 95). Ogni video è diverso: con la prova gratuita le misuri sui tuoi file. Metodo: <a href="BENCHMARKS.md">BENCHMARKS.md</a>.</sub>

## ✦ Come funziona

<table>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/app-stima.webp" alt="Stima del peso per ogni livello prima di comprimere">
      <h3>1 · Il peso lo sai prima</h3>
      Per ogni livello di qualità l'app prevede il peso finale e il tempo, comprimendo davvero dei
      brevi campioni e misurandoli.
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/app-in-corso.webp" alt="Una coda di video in compressione">
      <h3>2 · Comprimi una coda intera</h3>
      Trascina video o cartelle: MP4, MOV, MKV, AVI, WebM, HEVC 10 bit dei telefoni, ProRes.
      L'originale non viene mai toccato.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/app-risultato.webp" alt="Risultato: 87,3% più leggero con VMAF 96,13">
      <h3>3 · Ricevi il file verificato</h3>
      Un MP4 in AV1 accanto all'originale. Se resta sotto l'obiettivo di qualità, l'app ricomprime.
      Se non è almeno il 5% più leggero, resta l'originale.
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/app-qualita.webp" alt="VMAF nel tempo, fotogramma peggiore e tutte le misure">
      <h3>4 · Vedi ogni misura</h3>
      Qualità nel tempo, il fotogramma peggiore, la tendina tra originale e AV1 e il resoconto completo.
    </td>
  </tr>
</table>

### Quattro livelli, una sola misura

| Livello | Obiettivo VMAF | Per |
|:--|:--:|:--|
| **Fedele** | 97 | archivi e master |
| **Alta** · predefinito | 95 | uso di ogni giorno, pensato per non mostrare differenze |
| **Bilanciata** | 93 | web e social |
| **Compatta** | 90 | quando conta solo lo spazio |

## ✦ Alleggerisci SCORM <sup>servizio aggiuntivo</sup>

Per chi fa e-learning: prende un corso esportato da **Articulate, iSpring, Captivate** e altri
(SCORM 1.2, SCORM 2004, xAPI, cmi5) e lo restituisce più leggero, con gli stessi file, nomi e ordine.

<table>
  <tr>
    <td width="50%"><img src="docs/images/scorm-stima.webp" alt="Analisi del pacchetto SCORM e stima gratuita del risparmio"></td>
    <td width="50%"><img src="docs/images/scorm-risultato.webp" alt="Pacchetto SCORM più leggero del 71,8%, ogni video controllato"></td>
  </tr>
  <tr>
    <td><sub>Analisi e stima del risparmio gratuite, prima di comprare.</sub></td>
    <td><sub>46,9 MB → 13,3 MB. I video restano H.264: si vedono ovunque, Safari compreso.</sub></td>
  </tr>
</table>

## ✦ Fatto per fidarsi

| | |
|:--|:--|
| 🔒 **Sul tuo computer** | Video e corsi non vengono caricati da nessuna parte. La rete serve solo per la licenza. |
| 📏 **Misurato, non stimato a occhio** | VMAF su ogni fotogramma del file finito: media, 5° percentile, fotogramma peggiore. |
| 🪶 **Mai più pesante** | Un video già compresso al massimo, come quelli di WhatsApp, resta com'è. |
| 🗂️ **L'originale non si tocca** | Il nuovo file nasce con un nome provvisorio e prende il suo nome solo dopo la verifica. |
| ⏱️ **Tempo prevedibile** | La stima dice quanto ci vorrà. Il computer non va in stop durante la compressione. |
| 🎞️ **Ogni formato** | 8 e 10 bit, frame rate variabile, video verticali, audio 5.1, più lingue, sottotitoli. |

<div align="center">
  <br>
  <img src="docs/images/film.webp" alt="Il film di presentazione: una pila di fotogrammi si alleggerisce, uno per uno, e ogni fotogramma viene misurato" width="720">
  <br><sub>Il film del sito, disegnato fotogramma per fotogramma e compresso da NCPack Studio stesso:<br><b>da 369 MB senza perdita a 2,78 MB in AV1, VMAF 97,35.</b> · <a href="https://ncpack.roca.software/#film">Guardalo intero</a></sub>
</div>

## ✦ Come averlo

1. Richiedi la **[prova gratuita di 7 giorni](https://ncpack.roca.software/#demo)**: chiave e link per il download arrivano per email. Nessuna carta.
2. Installa NCPack Studio: **macOS 12+ su Apple silicon** o **Windows 64 bit**.
3. Incolla la chiave in **Licenza**. Fatto.

Finita la prova l'app resta utilizzabile nella versione gratuita (livello Alta, velocità Rapida, un video alla volta).

| Piano | Prezzo | |
|:--|:--:|:--|
| **Prova gratuita** | 0 € | tutte le funzioni per 7 giorni |
| **Personal** | 29 € una tantum | 1 computer, 1 anno di aggiornamenti |
| **Pro** | 59 € una tantum | 3 computer (anche macOS e Windows insieme), 2 anni di aggiornamenti |
| **Alleggerisci SCORM** | 149 € all'anno o 19 € a pacchetto | pacchetti illimitati, tutto sul tuo computer |

Nessun pagamento online: [scrivici](https://ncpack.roca.software/#demo) e ci accordiamo su pagamento e fattura.

## ✦ Problemi e idee

Hai trovato un problema o ti manca una funzione? **[Apri una segnalazione](../../issues/new/choose)**.
Non allegare mai video o corsi che non puoi condividere pubblicamente: descrivili (formato, risoluzione,
durata, da dove arrivano) oppure mandaci un esempio per email.

<br>

<div align="center">
  <sub>© 2026 NCPack Studio · ROCA Software. Tutti i diritti riservati.<br>
  Questo repository ospita documentazione, benchmark e segnalazioni; il codice sorgente dell'app non è pubblicato.</sub>
</div>
