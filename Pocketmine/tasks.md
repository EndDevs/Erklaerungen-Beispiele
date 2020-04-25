**Task**

Erklärung + Code

Einfacher RepeatingTask der unendlich weiterläuft
So wird dieser zum Beispiel gestartet:
```php
$this->getScheduler()->scheduleRepeatingTask();
```
Diese kann überall gestartet werden wo man es benötigt (event, command)

Die Task datei nennen wir Time.php
zuerst wie gewöhnlich komme die imports 
```php
use pocketmine\scheduler\Task;
```
die class sieht dann so aus
```php
class Time extends Task{}
```
Da man warscheinlich auf die Main zurückgreifen möchte benötigt man ein Konstrukt
```php
private $main;
public function __construct(Main $main){
    $this->main = $main;
}
```
Natürlich muss das und die Zeit beim starten des Tasks gegeben sein daher:
```php
$this->getScheduler()->scheduleRepeatingTask(new Time($this), 20);
```
Die Zahl 20 bedeutet die Anzahl der Zeit, die gezäht wird in ticks
20 ticks = 1 sekunde

Nun der Hauptteil vom Task
```php
public function onRun($ticks){}
```
Hier kommt der normale Code indem gefragt wird welche Zeit der Task hat
Beispiel:
```php
public function onRun($ticks){
    if($ticks == 5){
        $this->main->getServer()->broadcastMessage("Es wurden 5 Sekunde erreicht);
}
    if()...
}
```

Task stoppen/löschen:
```php
if($ticks == 20){
 $this->main->getServer()->getScheduler()->cancelTask($this->getTaskId());
}
```
