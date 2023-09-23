
# Основные команды Git

# CLONE
Клонирование только одной ветки из удаленного репозитория. 
Рассмотрим два способа. При вызове вы извлекатее все ветви и проверяте одну. Этот способ применяется реже, если есть большие объемы данных в нескольких ветках. 

Например, если в удаленном репозитории есть две ветки 10кБ и 10Гб, то при редактировании придется меньшей ветки придется копировать обе.
```
git clone --branch <branchname> url
or
git clone -b <branchname> url
```
Опция, которая будет использоваться далее доступна с версии 1.7.10 и более поздних версий.
```
git clone --single-branch --branch <branch name> url
git clone --single-branch --branch fifthAxes https://github.com/Ubersmurf2010/RoverM.git

```

# PUSH
Команда для настройки строгого соединения между удаленным репозиторием и локальной веткой
```
git push --set-upstream <local repo name> <branch name>
```
Теперь достаточно запустить, чтобы перенести изменения из заданной выше ветки в удаленный репозиторий
```
git push
```
Рассмотрим случай когда репозиторий клонирован (git clone) по https-адресу.
Если же клонирование локального репозитория произведено с помощью ssh, то предусмотрена перенастройка на https:
```
git remote set-url <local repo name, for example origin> https://github.com/Ubersmurf2010/githubHelper.git
git remote -v
```
В этом случае возможно вместо авторизации с помощью логина и пароля, которую удалили в августе 2021-ого года, использовать сгенирированный токен (причем, также, необходимо следить за тем, чтобы срок действия текущего токена не истек), в противном случае при выполнении команды push, git будет требовать пароль.
Password for 'https://<недействующий токен>':
Просто сгенируем новый токен и повтором команду ниже. 
```
sudo git push https://<token name>@github.com/Ubersmurf2010/RoverM.git <branch name> 
```
Если необходим пуш в определнную ветку, то после https-адреса укажем название ветки, куда необходимо сделать пуш.

# MERGE

# Слияние веток в локальном репозитории.
```
git pull
git checkout <main branch name>
git merge <second branch name>
```

# Git на Raspberry
При использовании предустановленного git на Pi os32-bit, после клонирования удаленного репозитория и попытки сделать коммит, может возникнуть ошибка Author identity unknown.
```
git config --global user.email "your email"
git config --global user.name "github username"
```

# Git init
Создадии новый репозиторий. В папке проекта выполним команды:
```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Ubersmurf2010/RPi_cam_streamer.git
git push -u origin main
```
Или же можно привязать уже существующий репозиторий.
```
git remote add origin https://github.com/Ubersmurf2010/RPi_cam_streamer.git
git branch -M main
```

