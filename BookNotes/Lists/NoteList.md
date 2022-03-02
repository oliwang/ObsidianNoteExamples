```button
name Add Note
type note(BookNotes/<%tp.date.now("YYYYMMDDHHmm") %>, split) template
action BookNoteTemplate
%%%%class dataview-button
templater true
```


<br>

```dataviewjs
dv.table(
	["File", "Author", "Type", "Status", "Tags"], 
	dv.pages('"BookNotes"')
		.sort(b => b.date)
		.sort(b => b.status)
		.map(b => [b.file.link.withDisplay(b.title), b.author, b.type, b.status.split("_")[1], b.tags.join(" ")])
)
```

