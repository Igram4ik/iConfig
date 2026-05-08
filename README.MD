# iConfig
Специальная конфигурационная библиотека на классовом редакторе

## Зачем и с чем его едят
- Классовый конфиг помогает использовать сериализированный переменные напрямую с Yaml конфиг-файлом без постоянных записей и вызовов методов load/unload
- Хорошая совместимость помогает сделать конфиг в виде класса очень удобным и практичным для некоторых решений с замудрёнными коллекциями (Collection/Set)
- Даёт возможность прекрасно (де-)сериализировать enums, обходя обходимость в проверках того, что было введено в Yaml-файле, конфиг разрешает строго только то, что есть в указанном Enum-классе

## Начать
### Добавить в Maven-проект:
> Default (jdk-18):
```xml
<dependency>
    <groupId>dev.igrammine.commons</groupId>
    <artifactId>iConfig</artifactId>
    <version>1.3.2</version>
    <classifier></classifier>
    <scope>compile</scope>
</dependency>
```
> jdk-14:
```xml
<dependency>
    <groupId>dev.igrammine.commons</groupId>
    <artifactId>iConfig</artifactId>
    <version>1.3.2</version>
    <classifier>jdk-14</classifier>
    <scope>compile</scope>
</dependency>
```

### Пример создания конфига:
```java
public class Example extends YamlConfig {
    @Ignore
    public static final Example CONFIG = new Example();
    
    @Create
    public SECTION SECTION;
    public static class SECTION {
        public String STRING = "Это строка.";
    }
}
```
Итог:
```yaml
section:
  string: Это строка.
```

Special for **[IGRAMMINE project](https://www.igrammine.ru/)**



