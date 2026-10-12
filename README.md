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

Or, just `build.gradle` only:

```gradle

plugins {
	id 'com.diffplug.spotless' version '8.8.0'
}

spotless {
	java {
		eclipse().configProperties("""
			org.eclipse.jdt.core.formatter.parentheses_positions_in_for_statment=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_enum_constant_declaration=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_catch_clause=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_annotation=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_method_delcaration=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_method_invocation=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_record_declaration=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_switch_statement=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_if_while_statement=preserve_positions
			org.eclipse.jdt.core.formatter.join_wrapped_lines=false
			org.eclipse.jdt.core.formatter.parentheses_positions_in_try_clause=preserve_positions
			org.eclipse.jdt.core.formatter.parentheses_positions_in_lambda_declaration=preserve_positions
			org.eclipse.jdt.core.formatter.tabulation.char=space
		""")
		removeUnusedImports()
		importOrder('java|javax', '', group)
		endWithNewline()
	}
}

```

## Format rules

- **Tab char**: Space
- **Parentheses positions**: Preserve position
- **Line wrapping**: 
	- Never join already wrapped line
