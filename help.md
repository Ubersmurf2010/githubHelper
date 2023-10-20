
# Основные команды Git

# git clone
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
# git push
Команда для настройки строгого соединения между удаленным репозиторием и локальной веткой
```
git push --set-upstream <local repo name> <branch name>
```
Теперь достаточно запустить, чтобы перенести изменения из заданной выше ветки в удаленный репозиторий
```
git push
git push origin <branch name>
```
Если необходим пуш в определнную ветку, то после https-адреса укажем название ветки, куда необходимо сделать пуш.

# git merge
```
git pull
git checkout <main branch name>
git merge <second branch name>
```

# git config (Raspberry)
При использовании предустановленного git на Pi os32-bit, после клонирования удаленного репозитория и попытки сделать коммит, может возникнуть ошибка Author identity unknown.
```
git config --global user.email "your email"
git config --global user.name "github username"
git config -l
```

# git init
Создадии новый репозиторий. В папке проекта выполним команды:
```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Ubersmurf2010/RPi_cam_streamer.git
git push -u origin main
```
# git remote add & git remote set-url
```
git remote add origin https://<username>:<token>@github.com/<username>/<repo name>.git
```
если неободимо поменять 
```
git remote set-url origin https://<username>:<token>@github.com/<username>/<repo name>.git
git remote -v
```



