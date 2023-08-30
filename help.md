
# Основные команды Git




Команда для настройки строгого соединения между удаленным репозиторием и локальной веткой
```
git push --set-upstream <local repo name> <branch name>
```
Теперь достаточно запустить, чтобы перенести изменения из заданной выше ветки в удаленный репозиторий
```
git push
```

Слияние веток в локальном репозитории.
```
git pull
git checkout <main branch name>
git merge <second branch name>
```
