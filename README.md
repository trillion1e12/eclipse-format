# eclipse-format
XML format files of Eclipse JDT

For using in [Spotless](https://github.com/diffplug/spotless/tree/main/plugin-gradle#eclipse-jdt)

The XML format configs were exported from Eclipse IDE by manually creating format configs through `Window > Preferences... > Java > Code Style > Formatter`

Download `eclipse-modified.xml` and use it with Spotless like this:

```gradle
spotless {
	java {
		eclipse().configFile('eclipse-modified.xml')
	}
}
```
