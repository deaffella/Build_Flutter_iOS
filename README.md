# Build_Flutter_iOS
___

1. Открыть терминал и установить зависимости:

	```
    do softwareupdate --install-rosetta --agree-to-license
	brew install cocoapods git
	
	# https://docs.flutter.dev/get-started/install/macos/desktop?tab=download
	mkdir -p ~/flutter_ios_development/ && cd ~/flutter_ios_development/ && wget https://storage.googleapis.com/flutter_infra_release/releases/stable/macos/flutter_macos_arm64_3.16.5-stable.zip
	
	unzip flutter_macos_arm64_3.16.5-stable.zip
	# add to env:
	cd ~/flutter_ios_development/ && export PATH="$PATH:`pwd`/flutter/bin"
	
	flutter upgrade
	
	sudo sh -c 'xcode-select -s /Applications/Xcode.app/Contents/Developer && xcodebuild -runFirstLaunch'
	sudo xcodebuild -license
	
	# Install Homebrew if necessary
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
	
	# Install ruby using Homebrew
	brew install ruby
	
	# Install cocoapods using Homebrew
	brew install cocoapods```

2. Скачать проект, разархивировать. Ожидаемое содержание проекта: ![01.png](images%2F01.png)
 
 
3. Перейти в `psgamer/ios/` и открыть с помощью `Xcode` проект `Runner.xcodeproj`. 
По необходимости следует установить средства разработки для ios.

5. Слева выбрать `Runner`, `Targets` -> `Runner`. Выбрать на вкладке `General` версию ios, 
билд только для iphone. Перейти в `Signing & Capabilities` и выбрать внутри `Team` свою команду разработки, 
которая привязана к аккаунту AppleID, а также ввести `Bundle Identifier` в формате `com.example.psgamer` (пример) ![01.png](images%2F01.png).

6. В терминале перейти в папку `Flutter/psgamer/` и собрать проект `flutter build ios`.

7. Вернуться в `Xcode`, выбрать конечное устройство для деплоя в верхней строке и нажать кнопку play. 
Проект в виде готового приложения зальется на подключенный iphone. ![03.png](images%2F03.png)

8. На iphone необходимо подтвердить сертификат разработчика, который был загружен с приложением. 
Заходим в `Настройки > Основные > VPN и управление устройством`, выбираем профиль с нашей учеткой AppleID, 
жмем доверять. Теперь можно запускать приложение.