Config erstellen: So geht´s!

Im ersten Schritt müssen wir die Klasse angeben:
```php
use pocketmine\utils\Config;
```
Dann benötigen wir erstmal eine Config, erstellen kann man die ganz Simple so:
```php
$config = new Config($this->getDataFolder()."$name.yml", Config::YAML);
```

Nun hast du eine Leere Config erstellt. Doch da du diese warscheinlich nicht leer haben willst musst du noch Sachen in der Config hinzufügen das geht so:
```php
$config->set("$name", $setto);
```
$setto kann ein String, eine Zahl oder eine Boolean sein. 
Jetzt hast du was in der Config festgelegt. Aber du musst dies auch Speichern und das machst du einfach mit 
```php
$config->save();
```

Jetzt hast du $setto als $name in der Config gespeichert. 
Wenn du jetzt $name herausfinden willst als was das gespeichert ist mache einfach:
```php
$config->get($name);
```
 Und jetzt kennst du die Basics der Config!

Falls du es noch nicht kapiert hast hier ein Beispiel:
```php
$config = new Config($this->getDataFolder()."$name.yml", Config::YAML);
$config->set("Name", "CodingSchule");
$config->save();

$name = $config->get("Name");
$player->sendMessage($name);
```
Naricht: CodingSchule
