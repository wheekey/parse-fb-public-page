# parse-fb-public-page
parser-example-fb-public-page


## Запускаем с виртуальным экраном.

1 - Переносим нужный docker файл из https://github.com/joyzoursky/docker-python-chromedriver
    Предпочтительно xvfb + python + selenium

2 - Билдим image. Этот же image можно будет использовать и для других проектов
```
 docker build --tag parse-fb-public-page:1.0 .
``` 
Лучше его назвать более общим названием. По типу selenium-xvfb-python

3 - Запускаем контейнер  
https://docs.docker.com/get-started/part2/
```
 docker run -d -t -w /usr/workspace -v $(pwd):/usr/workspace --name selenium-parser parse-fb-public-page:1.0
```

4 - Запустим нужный нам скрипт в контейнере
```
docker exec -ti selenium-parser python test_script.py
```

```
git clone https://github.com/joyzoursky/docker-python-chromedriver.git
$ cd docker-python-chromedriver
$ docker run -it -w /usr/workspace -v $(pwd):/usr/workspace joyzoursky/python-chromedriver:3.7 bash
```

# План по парсингу, что изучить
1 - Как тестировать Selenium
 https://pypi.org/project/lettuce_webdriver/
 http://lettuce.it/index.html                                       
2 - Как писать истый код на питоне   
https://github.com/zedr/clean-code-python                           
3 - Реализовать парсер публичной страницы fb                                                    