# Декомпозиция

![Текст описания](assets/decomposition.png)


## Компоненты
Компонент список
```jsx static
const List = ({className, children}) => {
    return (
        <div className={className}>
            {children}
        </div>
    );
}
```

компонент элемент
```jsx static
const Item = ({className, children}) => {
    return (
        <div className={className}>
            {children}
        </div>
    )
}
```

компонент Новостей
```jsx static
const News = () => {
    const dataList = [
        {
            "title": "Заголовок новости1",
            "description": "Описание новости1",
        },
        {
            "title": "Заголовок новости1",
            "description": "Описание новости1",
        },
        {
            "title": "Заголовок новости1",
            "description": "Описание новости1",
        },
        {
            "title": "Заголовок новости1",
            "description": "Описание новости1",
        }
    ];
    const newsList = dataList.map((item, index) => {
        return (
            <Item title={item.title} key={index} >
                <h3>{item.title}</h3>
            </Item>
        );
    });

    return (
        <List className="news">
            {newsList}
        </List>
    );
}
```

компонент поиска
```jsx static
const Search = () => {
    const searchTags = [
        "Видео", 
        "Картинки", 
        "Новости", 
        "Карты", 
        "Маркет", 
        "Переводчик", 
        "Эфир", 
        "ещё"
    ];

    const tabs = searchTags.map((item, index) => {
        return (
            <Item title={item} key={index}>
                <span>{item}</span>
            </Item>
        );
    });

    return (
        <div className="search">
            <List className="news">
                {tabs}
            </List>
            <Widget title="Поиск">
        </div>
    );
}
```

## Основная композация
```jsx static
const App = () => {
    return (
        <main>
            <News />
            <Search />
            <Widget title="Рекламный баннер">
            <Widget title="Погода">
            <.../>
        </main>
    )
}
```