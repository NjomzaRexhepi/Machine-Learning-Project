# Importimi tregtar në Doganat e Kosovës
<strong>Titulli i projektit</strong>: Bilanci tregtar në Doganat e Kosovës<br>
<strong>Universiteti</strong>: Universiteti i Prishtinës "Hasan Prishtina"<br>
<strong>Fakulteti</strong>: Fakulteti i Inxhinierisë Elektrike dhe Kompjuterike, Programi: Inxhinieri Kompjuterike dhe Softuerike, 2024/25<br>
<strong>Niveli</strong>: Master<br>
<strong>Lënda</strong>: Machine Learning<br>
<strong>Mësimdhënësit e lëndës</strong>: Prof. Dr. Lule Ahmedi, Ass. Dr. Mërgim Hoti<br>
<strong>Punuar nga</strong>: Erëblina Berisha, Njomza Rexhepi

![img.png](Results/img1.png)

Ky repository përmban projektin semestral për lëndën Machine Learning, me fokus në analizën e të dhënave lidhur me importet në Kosovë për vitet 2023-2024.
Burimi i të dhënave: Dogana e Kosovës - Open Data

https://dogana.rks-gov.net/OpenData/Index?id=4

## Dataset-i i përdorur për analizë
Dateseti përmban 11 kolona (atribute) dhe 233.639 rreshta (objekte).<br>

## Atributet e datasetit:<br>

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

Ky dataset përfaqëson të dhëna për importet në Kosovë për një periudhë të caktuar. Çdo rresht korrespondon me një artikull të importuar, duke përfshirë detaje rreth origjinës, llojit të produktit, sasisë, vlerës dhe taksave të lidhura. Dataset-i përfshin informacione specifike për produktet (p.sh., kodet tarifore) dhe informacione financiare (p.sh., vlera, taksat).



# Fazat e projektit
## Faza 1: Parapërpunimi i të dhënave

1. Tipet e të dhënave, kualiteti i të dhënave, numri i të dhënave të plota dhe ato null (të zbrazëta)<br>
2. Gjendja e të dhënave të lexueshme si tërësi, Strategjia e trajtimit të vlerave të zbrazëta, Mostrimi<br>
3. Pastrimi, normalizimi dhe transformimi i të dhënave.<br>
4. Detektimi i outliers dhe identifikimi i klasëve të shtrembëra.<br>

## Rezultatet nga faza 1:

Tipet e të dhënave në dataset:<br>
![img.png](Results/img.png)

Përshkrimi i të dhënave numerike:<br>
![img_1.png](Results/img_1.png)

Përshkrimi i të dhënave jonumerike:<br>
![img_2.png](Results/img_2.png)

Përqindja e rreshtave duplikatë:<br>
![img_3.png](Results/img_3.png)

Vlerat e zbrazëta nëpër kolona:<br>
![img_4.png](Results/img_4.png)![img_5.png](Results/img_5.png)<br>
![img_6.png](Results/img_6.png)

Standardizimi apo normalizimi i atributit Kodi Tarifor, për përpunim më të lehtë:<br>
![img_7.png](Results/img_7.png)

Frekuencat e kategorive të atributit Origjina:<br>
![img_8.png](Results/img_8.png)![img_9.png](Results/img_9.png)

Vizualizimi i marrëdhënies midis dy atributeve numerike:<br>
![img_10.png](Results/img_10.png)

Matrica e korrelacionit:<br>
![img_11.png](Results/img_11.png)

Procesi i mbushjes së të dhënave ku vlerat që mungojnë (null) në kolonën 'Sasia' parashikohen bazuar në veçori të tjera (p.sh., 'Netweight', 'Vlera Mallrave', 'Taksa TVSH-së') duke përdorur një model RandomForestRegressor:<br>
![img_12.png](Results/img_12.png)

Detektimi i outliers:<br>
![img_13.png](Results/img_13.png)

Trajtimi i outliers duke përdorur metodën e IQR:<br>
![img_15.png](Results/img_15.png)

Koeficienti i anueshmërisë:<br>
![img_16.png](Results/img_16.png)

Transformimi i të dhënave në kolonat Origjina dhe Kodi Tarifor:<br>
![img_17.png](Results/img_17.png)

Identifikimi i klasëve të shtrembëra:<br>
![img_19.png](Results/img_19.png)
![img_20.png](Results/img_20.png)
![img_21.png](Results/img_21.png)
![img_22.png](Results/img_22.png)

Histogramet për kolonën Netweight:<br>
![img_23.png](Results/img_23.png)
![img_24.png](Results/img_24.png)






