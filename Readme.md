Библиотека которая позволяет более просто получить динамический веб-контент.

Для использования необходимо скачать chromedriver. В дальнейшем будет поддержка и других решений.
Затем инициализировать парсер: 
driver = '/path/to/chromedriver'
parse = DynamicWebParse(driver)

Далее можно запустить как режим с отслеживанием парсинговой страницы, так и без него для этого есть 2 соотвтетствующие команды:
parse.makeVisibleDriver()
parse.makeUnvisibleDriver()

Для загрузки страницы необходимо применить следующию команду:
requests.allwaysLoadPage(link)
 при этом следующим параметром можно передать время через которое чтоит обрвать загрузку
 
И получиьт элементы страницы можно следующим образом:
requests = Requests(parse.getDriver())
requests.getElems(xpath_str)
в дальнейшем будет также добавлены и другие способы получения данных/

Также есть возможность совершать клики и тому подобные действия:
actionChainsToElem(self, action, elem):
        act = action(elem)
        act.perform()

actionChainsToElem(self, action, elem):
        act = action(elem)
        act.perform()

moveToElem(self, elem) - перейти на элемент скролом
getElem(self, getData, breakTime=None) - получить 1 элемент
getElems(self, getData, breakTime=None) - получить много элементов
clickElem(self, getData, breakTime=None) - нажать на элемент
submitElem(self, getData, breakTime=None) - подтвердить элемент
clickElems(self, getData, breakTime=None) - нажать на мого элементов