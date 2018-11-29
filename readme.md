использую node 4.5
для удобной смены версии ноды есть nvm- https://github.com/creationix/nvm

1-создаем папку <имя папки>
2-npm init
3-проставляем права(chmod 777 <имя папки>), у меня почему-то все время слетают, sudo решает эту проблему
4-sudo npm install iobroker --unsafe-perm (эту и последующие команды npm делаем     из корня папки <имя папки>, команды iobroker- там где он доступен) после этого    в корне должен появиться исполнительный файл iobroker
  ./iobroker start
  ./iobroker stop
  на этом этапе брокер должен запускаться возвращать пид
  другие команды https://github.com/ioBroker/ioBroker/wiki/Console-commands
5-sudo npm install iobroker.google-sharedlocations
  sudo npm install iobroker.admin
  sudo npm install iobroker.js-controller
  Устанавливаем адаптеры для брокера
  после этого ./iobroker add google-sharedlocations
  после успешной установки и добавления они должны отображаться в выводе
  ./iobroker list adapters
6-в отдельной вкладке терминала запустим админку
    node node_modules/iobroker.js-controller/controller.js
    это даст <имя хоста>
    заходим на <имя хоста>:8081 - видим админку iobroker, не нашел там ничего интересного, не знаю будет ли она нам полезна


https://github.com/ioBroker/ioBroker/wiki/Console-commands#iobroker-start-adapternameinstance

./iobroker start google-sharedlocations.0

7- через админку можно редактировать инстанс на русском раздел почему-то называется "настройки"
гаечный ключ по googlesharedlocations
и откроется окошко с логином и кнопкой проверить соединение 