
PrettyDialog  adalah Android doalog library yang dikembangkan dari https://github.com/mjn1369/PrettyDialog

Penggunaan app modul
## Download
### Gradle:
tambahkan maven di level project project build.gradle:
```
allprojects {
   repositories {
      maven { url "https://jitpack.io" }
   }
}
```

kemudian tambahkan baris ini di level app build.gradle:

```
dependencies {
    implementation 'com.github.ahmadbasarudin:PrettyDialog:1.0.1'
}
```

Penggunaan di level logic

1. sederhana

```
new PrettyDialog(this)
	.setTitle("PrettyDialog Title")
	.setMessage("PrettyDialog Message")
	.showDialog();
```


### Mengganti Icon:
```
.setIcon(R.drawable.pdlg_icon_info)
```

```
.setIconTint(R.color.pdlg_color_green)
```

### Callback waktu icon dicallback:

```
.setIconCallback(new PrettyDialogCallback() {
	    @Override
	    public void onClick() {
		    //apa yang akan terjadi setelah icon diklik
	    }
	})
```


- level peletakan:
```
.setIcon(
	R.drawable.pdlg_icon_info,     // icon resource
	R.color.pdlg_color_green,      // icon tint
	new PrettyDialogCallback() {   // icon OnClick listener
	    @Override
	    public void onClick() { 
		    //apa yang akan terjadi setelah icon diklik
	    }
	})
```

### Menambah Buttons:
- anda dapat menambahkan button tak terbatas kedalam dialog: 

```
// OK button
.addButton(
		"OK",					// button text
		R.color.pdlg_color_white,		// button text color
		R.color.pdlg_color_green,		// button background color
		new PrettyDialogCallback() {		// button OnClick listener
		    @Override
		    public void onClick() {
		    //apa yang akan terjadi setelah tombol OK diklik
		    }
		}
	)
	
// Cancel button
.addButton(
		"Cancel",
		R.color.pdlg_color_white,
		R.color.pdlg_color_red,
		new PrettyDialogCallback() {
		    @Override
		    public void onClick() {
			  // Dismiss
		    //apa yang akan terjadi setelah tombol CANCEL diklik
		    }
		}
	)
	
// 3rd button
.addButton(
		"Option 3",
		R.color.pdlg_color_black,
		R.color.pdlg_color_gray,
		null
	);
```
