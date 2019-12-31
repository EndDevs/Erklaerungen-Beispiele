Heal und Feed als Command -Tutorial

Also ganz am Anfang musst du eine Namespace nehmen in meinem Fall 
```php
namespace FleekRush;
```
als nächstes musst du alle Klassen angeben diese sind
```php
use pocketmine\plugin\PluginBase;
  use pocketmine\command\Command;
  use pocketmine\command\CommandSender;
```


Nun kommt wie gewohnt 
```php
class commands extends PluginBase {
}
```


Als erste Funktion nehmen wir gleich den Command also heal und Feed als erstes öffnen wir die Funktion also :
```php
public function onCommand(CommandSender $sender,Command $cmd,string $label,array $args): bool{
```


Als nächstes machst du den Command dafür benutz ich :
```php
switch($cmd->getName()){
         case "heal":
```


   Dann musst du angeben was dann gemacht werden soll also :
```php
switch($cmd->getName()){
            case "heal":
                $sender->setHealth(20);
              break;
    return true;
}   //Klammer wegen der onCommand Funktion
}  //Klammer wegen class command extends PluginBase
```


Das wars jetzt nurnoch in der plugin.yml regestrieren und schon sollte es funktionieren!
