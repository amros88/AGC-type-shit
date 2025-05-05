# Informatik Logbog

## Kryptering
### Kriterier for kryptering  

![Skema fra systime](https://github.com/user-attachments/assets/3e3f2bb2-bf0a-4cac-98db-352eb7a46764)

[Link til kilde på systime.dk](https://informatik.systime.dk/?id=876)

* Fortrolighed - Kun dem vi ønsker kan læse beskeden.
* Dataintegritet - Ingen kan ændre min besked.
* Uafviselighed - Vi kan være sikre på at afsenderen er den den siger den er. 
* Autenticitet - Vi kan være sikre på at beskeden er uændret
  
Sikkerhed   
- Ingen kan ændre min besked. Privathed   
- Ingen andre end den man ønsker kan læse beskederne. Verificérbarhed
- Vi kan være sikre på at afsenderen er den den siger den er. Hemmelighed
- Ingen kan se hvem der skriver sammen.

**Symmetrisk vs Asymmetrisk kryptering**  
*Symmetrisk (FX AES):*   
Samme nøgle til kryptering og dekryptering - Afsender og modtager deler nøglen

*Asymmetrisk (FX RSA): Privat+Offentlig nøglepar:*  
Data krypteret med den ene nøgle kan kun dekrypteres med anden nøgle fra et nøglepar. dvs alle med min offentlige nøgle kan verificere at jeg har krypteret beskeden med min private nøgle og alle med min offentlige nøgle kan sende beskeder som det kun er mig der kan dekryptere

## 3D

### Modellering
Link til de bedste 3d-modeller i branchen (OnShape):  
https://cad.onshape.com/documents?nodeId=67c55623dc8d915582f3074f&resourceType=resourceuserowner    
  
### Hvad er OnShape?
- Cloud-baseret CAD-software til 3D-modellering.
- Bruges til at designe mekaniske komponenter og produkter.
- Understøtter parametrisk design og samarbejde i realtid.

### Grundlæggende værktøjer i OnShape
- **Sketch**: Tegn 2D-profiler, der danner grundlaget for 3D-modeller.
- **Extrude**: Trækker en 2D-skitse ud i en 3D-form.
- **Revolve**: Roterer en skitse omkring en akse for at danne en 3D-geometri.
- **Fillet/Chamfer**: Afrund eller skær kanter af modeller.
- **Pattern**: Kopier elementer i en bestemt retning eller rundt om en akse.

### Workflow i OnShape
1. **Opret et nyt dokument**.
2. **Lav en skitse** på en valgt planeflade.
3. **Brug ekstrudering eller andre funktioner** til at skabe en 3D-model.
4. **Tilføj detaljer** som afrundinger eller huller.
5. **Eksporter som STL** til 3D-print.

### 3D-printing basics
- **Filformat**: 3D-printere bruger typisk STL eller OBJ.
- **Slicing-software**: Programmer som Cura eller PrusaSlicer oversætter STL-filer til G-code.
- **Materialer**: PLA, ABS, PETG og TPU er almindelige filamenttyper.
- **Printerindstillinger**:
  - **Lagtykkelse**: Bestemmer kvalitet og printtid.
  - **Fyldningsgrad**: Hvor solidt printet skal være.
  - **Understøtninger**: Nødvendigt for overhængende dele.

### Tips til succesfuldt 3D-print
- Sørg for at **kalibrere din printer** (bedplate og ekstruder).
- Brug **rigtige temperaturindstillinger** for filamentet.
- Tjek at første lag sidder ordentligt fast for at undgå fejl.
- Optimer designet for printvenlighed, fx undgå for store overhæng.

## Programmering
Programmeringen foregik i p5.js, hvilket basically er Javascript.  
Top notch kode: https://editor.p5js.org/raminabhani3/sketches

### Hvad er p5.js?
- p5.js er et JavaScript-bibliotek til kreativ kodning.
- Det bruges til grafiske projekter, interaktive kunstværker og animationer.
- Baseret på Processing, men tilpasset webteknologier.

### Grundlæggende struktur i p5.js
En p5.js skitse har typisk to vigtige funktioner:

#### 1. **setup()**
- Kører én gang ved start.
- Bruges til at definere lærredets størrelse og initialisere variabler.
```javascript
function setup() {
  createCanvas(400, 400);
  background(220);
}
```

#### 2. **draw()**
- Kører i en løkke efter `setup()`.
- Bruges til at tegne elementer på lærredet.
```javascript
function draw() {
  ellipse(mouseX, mouseY, 50, 50);
}
```

### Tegning med p5.js
#### Former
- **ellipse(x, y, bredde, højde)** – Tegner en ellipse.
- **rect(x, y, bredde, højde)** – Tegner et rektangel.
- **line(x1, y1, x2, y2)** – Tegner en linje.
- **point(x, y)** – Tegner et punkt.

Eksempel:
```javascript
function draw() {
  background(220);
  rect(50, 50, 100, 100);
  ellipse(200, 200, 50, 50);
}
```

### Interaktivitet
p5.js understøtter brugerinput som mus og tastatur.
#### **Mus-input**
- `mouseX`, `mouseY`: Musens position.
- `mousePressed()`: Funktion, der aktiveres ved museklik.
```javascript
function mousePressed() {
  background(random(255), random(255), random(255));
}
```

#### **Tastatur-input**
- `keyPressed()`: Funktion, der aktiveres, når en tast trykkes.
```javascript
function keyPressed() {
  if (key === 'r') {
    background(255, 0, 0);
  }
}
```

### Animation i p5.js
- `frameRate(fps)`: Sætter antallet af frames per sekund.
- `fill(r, g, b)`: Angiver fyldfarve.
- `stroke(r, g, b)`: Angiver kantfarve.

Eksempel:
```javascript
let x = 0;
function draw() {
  background(220);
  ellipse(x, height / 2, 50, 50);
  x += 2;
}
```

### Avancerede funktioner
- **Arrays** til at gemme og manipulere flere elementer.
- **Klasser** til at organisere kode bedre.
- **Biblioteker** for ekstra funktionalitet (f.eks. lyd, maskinlæring).

### Vektorer
- p5.js har en indbygget `p5.Vector` klasse til at arbejde med vektorer.
- Bruges til at repræsentere position, hastighed og acceleration.

Eksempel:
```javascript
let position;

function setup() {
  createCanvas(400, 400);
  position = createVector(200, 200);
}

function draw() {
  background(220);
  ellipse(position.x, position.y, 50, 50);
}
```

#### Vektor-operationer
- **Addition**: `v1.add(v2);`
- **Subtraktion**: `v1.sub(v2);`
- **Multiplikation**: `v1.mult(scalar);`
- **Division**: `v1.div(scalar);`
- **Normalisering**: `v1.normalize();`

Eksempel med bevægelse:
```javascript
let position, velocity;

function setup() {
  createCanvas(400, 400);
  position = createVector(200, 200);
  velocity = createVector(2, 3);
}

function draw() {
  background(220);
  position.add(velocity);
  ellipse(position.x, position.y, 50, 50);
}
```

## Arduino
### Hvad er Arduino?
- Arduino er en open-source platform til elektronikprojekter.
- Består af både hardware (mikrocontroller-baserede boards) og software (Arduino IDE).
- Bruges til at styre sensorer, motorer, lys og andre elektroniske komponenter.

### Grundlæggende funktioner i Arduino
Arduino-kode består af to hovedfunktioner:

#### 1. **setup()**
- Kører én gang ved start.
- Bruges til at initialisere pins, kommunikation osv.
```cpp
void setup() {
  pinMode(13, OUTPUT); // Sætter pin 13 som output
}
```

#### 2. **loop()**
- Kører i en uendelig løkke efter `setup()`.
- Bruges til at kontrollere komponenter og reagere på input.
```cpp
void loop() {
  digitalWrite(13, HIGH); // Tænder LED
  delay(1000); // Venter 1 sekund
  digitalWrite(13, LOW); // Slukker LED
  delay(1000); // Venter 1 sekund
}
```

### Blinkende LED (Hello World for Arduino)
- Kræver en Arduino og en LED (eller brug den indbyggede LED på pin 13).
- Koden tænder og slukker LED'en med 1 sekunds mellemrum.
```cpp
void setup() {
  pinMode(13, OUTPUT);
}

void loop() {
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```

### Grundlæggende hardware-komponenter
- **Digital Output**: Styring af LED, motorer, buzzere (HIGH/LOW).
- **Digital Input**: Læsning af knapper, sensorer (HIGH/LOW).
- **Analog Input**: Læsning af værdier fra potentiometre, temperatur- og lyssensorer (0-1023).
- **Analog Output (PWM)**: Justering af LED-lysstyrke eller motorhastighed (0-255).

### Seriel kommunikation
- Bruges til at sende data mellem Arduino og en computer.
```cpp
void setup() {
  Serial.begin(9600); // Starter seriel kommunikation
}

void loop() {
  Serial.println("Hello, Arduino!"); // Sender tekst
  delay(1000);
}
```

## Innovation
### De 4 p'er

<img src="https://github.com/user-attachments/assets/e243f2a3-9345-4252-9b40-1ecd373160c5" width="600" height="500">

#### Produkt
Her har vi fokus på ændringen af et produkt.
Et eksempel er vores føromtalte smartphone. De enkelte dele, såsom gps, telefon og spil, findes i forvejen, men samlet i en smartphone er der tale om et andet produkt.

#### Proces
Her er der fokus på ændringen af en proces i en virksomhed.
Et eksempel er firmaet ChiliHouse. De har ændret deres arbejdsprocesser, fordi handlen ikke længere foregår i en fysisk butikker, men på nettet.

#### Position
Her er fokus på ændringen af den position (kontekst) it-systemet anvendes i set fra brugerens/kundens synsvinkel.
Et eksempel er is. Her er fokus på ændringen fra, at is er slik til børn, til at is er en luksusspise for voksne.

#### Paradigme
Her er fokus på ændringen af den grundlæggende selvforståelse i en virksomhed.
Et eksempel er firmaet IBM. Firmaet startede som producent af hardware, men i dag sælger de i højere grad software og konsulentydelser.
