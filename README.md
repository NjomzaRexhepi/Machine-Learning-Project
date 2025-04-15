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
Dateseti përmban 11 kolona (atribute) dhe 233.638 rreshta (objekte).<br>

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

**Përmbledhje e Dataset-it dhe Tipet e të Dhënave**

**Përshkrim:<br>**
Përmbledhje e strukturës së dataset-it, e cila përmban gjithsej 233,638 rreshta dhe 11 kolona. Kolonat janë të ndara sipas tipeve të të dhënave:

* **Integer (int64)**: VITI dhe MUAJI, që përfaqësojnë vitin dhe muajin përkatës.<br>
* **Float (float64)**: Kolona numerike si Sasia, Vlera Mallrave, Netweight, dhe kolonat e ndryshme të taksave (Taksa Doganës, Taksa Akcizës, Taksa TVSH-së) përmbajnë të dhëna numerike vazhduese.<br>
* **Object**: Kolonat kategorike ose me tekst si Regjimi, Origjina, dhe Kodi Tarifor ruhen si tipe objekt.

Njohja e tipeve të të dhënave është një hap thelbësor përpara përpunimit, pasi ndikon në mënyrën se si do të kodohen, normalizohen ose transformohen më tej këto të dhëna.
![img.png](Results/img.png)

**Statistikat Përshkruese të Kolonave Numerike**

**Përshkrim:**<br>
Statistikat përshkruese të kolonave numerike në dataset, të gjeneruara përmes funksionit df.describe(). Ky hap ndihmon për të kuptuar shpërndarjen dhe karakteristikat kryesore të të dhënave numerike:<br>
* **count**: Numri i vlerave jo-munguese për secilën kolonë.
* **mean**: Mesatarja e vlerave në kolonë.
* **std**: Devijimi standard, që tregon shpërndarjen e të dhënave rreth mesatares.
* **min**: Vlera më e vogël në kolonë.
* **25% / 50% (medianë) / 75%**: Kuartilat që tregojnë përqindjet e shpërndarjes së të dhënave.
* **max**: Vlera maksimale në kolonë.

Këto statistika ndihmojnë në identifikimin e vlerave jashtëzakonisht të larta (outliers), shpërndarjes jo të balancuar, dhe mund të sinjalizojnë nevojën për normalizim ose transformime të tjera të të dhënave.<br>
![img_1.png](Results/img_1.png)

**Statistikat Përshkruese për Kolonat Kategorike (Objekt)**

**Përshkrim:**<br>
Statistikat përshkruese për kolonat me tip object në dataset, të gjeneruara me df.describe(include=['O']). Këto kolona zakonisht përmbajnë vlera tekstuale ose kategorike, si Regjimi, Origjina dhe Kodi Tarifor.<br>
* **count**: Numri total i vlerave jo-munguese për secilën kolonë.
* **unique**: Numri i vlerave të ndryshme (unike) në kolonë.
* **top**: Vlera që shfaqet më shpesh (modaliteti).
* **freq**: Frekuenca e vlerës më të shpeshtë.

![img_2.png](Results/img_2.png)

**Rreshtat e Përsëritur**

**Përshkrim:**
Përqindja e rreshtave të përsëritur në dataset, e llogaritur me df.duplicated(). Rreshtat e përsëritur mund të ndikojnë negativisht në analizë dhe zakonisht duhen hequr për të ruajtur saktësinë e të dhënave.<br>
![img_3.png](Results/img_3.png)

**Mungesa e të Dhënave në Kolonat Numerike dhe Kategorike**

**Përshkrim:**<br>
Analiza e mungesës së të dhënave në dataset për kolonat numerike dhe kategorike:

* **Kolonat Numerike**: Mungesat janë llogaritur me df.select_dtypes(include=['number']).isnull().sum().
* **Kolonat Kategorike**: Mungesat janë llogaritur përmes df.select_dtypes(include=['object', 'category']).isnull().sum().

Gjithashtu, një heatmap vizualizon mungesat për çdo rresht dhe kolonë të dataset-it, duke ndihmuar në identifikimin e përqindjes së mungesave.<br>
![img_4.png](Results/img_4.png)![img_5.png](Results/img_5.png)<br>
![img_6.png](Results/img_6.png)

**Zëvendësimi i Karaktereve të Shqipërisë në Kolonën 'Kodi Tarifor'**

**Përshkrim:**<br>
Ky kod zëvendëson karakteret speciale të shqipes në kolonën Kodi Tarifor me karaktere ASCII të zakonshme. Përdorimi i funksionit replace_albanian_chars ndihmon në normalizimin e të dhënave për përpunim më të thjeshtë dhe kompatibilitet më të mirë me algoritmet e përpunimit të tekstit.<br>
![img_7.png](Results/img_7.png)

**Shpërndarja e Kategorive për kolonën 'Origjina'**

**Përshkrim:**<br>
Ky kod vizualizon shpërndarjen e kategorive për kolonën Origjina me një diagramë countplot, duke treguar frekuencën e secilës kategori. Gjithashtu, ai printon numrin dhe përqindjet e kategorive, duke ndihmuar në analizën e shpërndarjes së vlerave të kategorive.<br>
![img_8.png](Results/img_8.png)![img_9.png](Results/img_9.png)

**Scatter Plot: Sasia vs. Vlera Mallrave**

**Përshkrim:**<br>
Ky diagram scatter tregon lidhjen ndërmjet kolonave Sasia (sasia e mallrave) dhe Vlera Mallrave (vlera e mallrave). Ky vizualizim ndihmon për të parë nëse ka ndonjë tendencë ose lidhje midis këtyre dy variablave në dataset.<br>
![img_10.png](Results/img_10.png)

**Matrica e Korrelacionit**

**Përshkrim:**<br>
Ky kod krijon një matrice korelacioni për kolonat Sasia, Vlera Mallrave, Netweight, Taksa Doganës, dhe Taksa TVSH-së. Matrica tregon lidhjen midis këtyre variablave numerikë, duke ndihmuar në identifikimin e korelacioneve pozitive ose negative midis tyre.<br>
![img_11.png](Results/img_11.png)

**Parashikimi i Mungesave në Kolonën 'Sasia'**

**Përshkrim:**<br>
Trajtimi i mungesave në kolonën Sasia duke përdorur një model RandomForestRegressor për të parashikuar vlerat e munguara. Fillimisht, ai ndan datasetin në dy pjesë: një pa mungesa dhe një me mungesa. Pastaj, përdor StandardScaler për normalizimin e të dhënave dhe përdor Random Forest për të parashikuar vlerat e munguara. Në fund, ai bashkon datasetin dhe printon numrin e vlerave të parashikuara që janë negative.<br>
![img_12.png](Results/img_12.png)

**Identifikimi i Përjashtuesve për Kolonën 'Sasia'**

**Përshkrim:**<br>
Përdoret metoda IQR (Interquartile Range) për të identifikuar përjashtuesit (outliers) në kolonën Sasia. IQR llogaritet si diferenca midis Q3 (75% e percentilit) dhe Q1 (25% e percentilit). Vlerat që janë më të vogla se Q1 - 1.5 * IQR ose më të mëdha se Q3 + 1.5 * IQR konsiderohen përjashtues. Ky proces ndihmon në zbulimin e vlerave ekstreme që mund të ndikojnë në analizat e mëtejshme.<br>
![img_13.png](Results/img_13.png)

**Përjashtuesit pas Trajtimit për Kolonën 'Sasia'**

**Përshkrim:**<br>
Ky kod përdor metodën IQR (Interquartile Range) për të identifikuar dhe filtruar përjashtuesit në kolonën Sasia pas trajtimit. Vlerat jashtë kufijve të llogaritur nga IQR (më të ulëta se Q1 - 1.5 * IQR ose më të larta se Q3 + 1.5 * IQR) konsiderohen si përjashtues dhe janë shfaqur në rezultatin përfundimtar.<br>
![img_15.png](Results/img_15.png)

**Koeficienti i Anueshmërisë për Kolonat Numerike**

**Përshkrim:**<br>
Ky kod llogarit koeficientin e anueshmërisë për kolonat numerike në dataset. Koeficienti i anueshmërisë mat shpërndarjen e të dhënave dhe ndihmon në identifikimin e asimetrisë së shpërndarjes:

* **Pozitiv**: shpërndarje e shtrirë majtas (ngjitja më e madhe është në të djathtë).
* **Negativ**: shpërndarje e shtrirë djathtas (ngjitja më e madhe është në të majtë).

![img_16.png](Results/img_16.png)

**Përditësimi i Kolonës 'Origjina'**

**Përshkrim:**<br>
Ky kod përditëson kolonën Origjina duke ndarë vlerat që janë të ndara me " - " dhe duke ruajtur vetëm pjesën e dytë (pas " - "). Kjo ndihmon në përpunimin dhe normalizimin e të dhënave kur ekzistojnë elementë të ndarë në një fushë që kërkojnë analizë të veçantë.<br>
![img_17.png](Results/img_17.png)

**Analiza Vizuale për Kolonat Numerike**

**Përshkrim:**<br>
Dy grafike për secilën kolone numerike në dataset:
1. Kernel Density Estimation (KDE) për të treguar shpërndarjen e mundshme të të dhënave dhe për të vlerësuar normalitetin e shpërndarjes.
2. Box Plot për të analizuar shpërndarjen dhe mundësinë e pranisë së përjashtuesve (outliers). Të dyja këto grafike ndihmojnë në vlerësimin e natyrës së shpërndarjes së të dhënave.
![img_19.png](Results/img_19.png)
![img_20.png](Results/img_20.png)
![img_21.png](Results/img_21.png)
![img_22.png](Results/img_22.png)

**Histogrami i Shpërndarjes së të Dhënave për 'Netweight'**

**Përshkrim:**<br>
Kjo figurë vizualizon shpërndarjen e të dhënave për kolonën Netweight përpara dhe pas pastrimit të të dhënave.
* Histogrami para pastrimit tregon shpërndarjen origjinale të të dhënave.
* Histogrami pas pastrimit tregon shpërndarjen e të dhënave pas trajtimit, ku është aplikuar një transformim logaritmik për të përmirësuar normalitetin e shpërndarjes.<br>
![img_23.png](Results/img_23.png)
![img_24.png](Results/img_24.png)



## Faza 2: Trajnimi i modeleve me të dhëna

Në këtë fazë, ne fokusohemi në trajnimin e modeleve të ndryshme të Machine Learning duke përdorur të dhënat e përpunuara nga Faza 1. Qëllimi kryesor është të zgjedhim modelin më të mirë që mund të parashikojë me saktësi rezultatin e dëshiruar.

### Hapat kryesorë të kësaj faze:
#### Ndarja e të Dhënave

Të dhënat ndahen në grupe trajnimi dhe testimi (p.sh., 80% për trajnim, 20% për testim).

Mund të përdoret edhe validimi në k-fold cross-validation për të rritur besueshmërinë e rezultateve.

#### Zgjedhja e Modeleve

Testojmë algoritme të ndryshme të Machine Learning si:

Modele lineare (regresion linear, logistic regression)

Pemë vendimesh (Decision Trees, Random Forest, XGBoost)

Mënyra të thella të të nxënit (Neural Networks)

Metoda klasike (SVM, k-NN)




