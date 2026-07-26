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

## Format rules

- **Tab char**: Space
- **Parentheses positions**: Seperate lines if wrapped
- **New line > Keep braced code on one line**: If empty
- **Line wrapping**: 
	- Never join already wrapped line
	- Many is: Wrap all element, every element on a new line (48)