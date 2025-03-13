# Importimi tregtar në Doganat e Kosovës

Titulli i projektit: Bilanci tregtar në Doganat e Kosovës<br>
Universiteti: Universiteti i Prishtinës "Hasan Prishtina"<br>
Fakulteti: Fakulteti i Inxhinierisë Elektrike dhe Kompjuterike, Programi Kompjuterik, 2024/25<br>
Niveli i studimeve: Master<br>
Lënda: Machine Learning<br>
Mentor: Prof.Dr.Lule Ahmedi, Prof.Dr.Mërgim Hoti<br>
Anëtarët e grupit punues: Erëblina Berisha, Njomza Rexhepi

![image](https://github.com/user-attachments/assets/9fb85b80-737f-459a-9d43-967b7e7ccff1)

Ky repository përmban projektin semestral për lëndën Machine Learning, me fokus në të dhënat lidhur me importet në Kosovë për vitet 2023-2024.
Burimi i të dhënave: https://dogana.rks-gov.net/OpenData/Index?id=4

## Dataset-i i përdorur për analizim
Dateseti përmban 11 kolona (atribute) dhe 233.639 rreshta (objekte):<br>

## Kolonat e datasetit:<br>

VITI: Viti i transaksionit.

MUAJI: Muaji i transaksionit.

Regjimi: Regjimi ose lloji i transaksionit (p.sh., IM4, që ndoshta tregon një kategori specifike importi).

Origjina: Vendi i origjinës së mallrave të importuara (p.sh., CN - KINA, PL - POLONIA, etj.).

Kodi Tarifor: Një kod specifik i produktit që përdoret për klasifikimin doganor (p.sh., 8807100090, 8529101190).

Sasia: Sasia e mallrave të importuara (në disa raste, kjo është bosh, që mund të tregojë shërbime ose artikuj jo të matshëm).

Vlera Mallrave: Vlera monetare e mallrave të importuara.

Netweight: Pesha neto e mallrave (në disa raste, kjo është bosh ose zero).

Taksa Doganës: Taksa doganore e aplikuar për mallrat.

Taksa Akcizës: Taksa e akcizës e aplikuar për mallrat (në shumicën e rasteve, kjo është zero).

Taksa TVSH-së: Taksa mbi vlerën e shtuar (TVSH) e aplikuar për mallrat.

## Përshkrimi i Dataset-it:

Ky dataset përfaqëson të dhëna për importet për një periudhë të caktuar. Çdo rresht korrespondon me një artikull të importuar, me detaje rreth origjinës, llojit të produktit, sasisë, vlerës dhe taksave të lidhura. Dataset-i përfshin informacione specifike për produktet (p.sh., kodet tarifore, përshkrimet) dhe informacione financiare (p.sh., vlera, taksat).

# Fazat e projektit
## Faza 1: Parapërpunimi i të dhënave
1. Pastrimi, normalizimi dhe transformimi i të dhënave.<br>
2. Trajtimi i vlerave që mungojnë, outliers dhe shkallëzimit të veçorive.<br>
3. Analiza e të dhënave eksploruese (EDA) dhe përzgjedhja e veçorive.<br>

## Faza 2: Trajnimi i modelit
...

## Faza 3: Ritrajnimi i modelit
...

