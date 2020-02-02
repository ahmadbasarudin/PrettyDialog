
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


```
new PrettyDialog(this)
	.setTitle("PrettyDialog Title")
	.setMessage("PrettyDialog Message")
	.showDialog();
```

### Mengganti Suara:
```
.setSound(R.raw.error)
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

### Menambah Button:
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

### Contoh Penerapan:

```
new PrettyDialog(this)
                .setIcon(
                        R.drawable.pdlg_icon_info,    // Icon resource
                        R.color.pdlg_color_green,      // Icon tint
                        new PrettyDialogCallback() {  // Icon OnClick listener
                            @Override
                            public void onClick() {
                                // Do what you gotta do
                            }
                        })
                .setTitle("PrettyDialog Title")
                .setMessage("PrettyDialog Message")
                .addButton(
                        "OK",
                        R.color.pdlg_color_white,
                        R.color.pdlg_color_green,
                        new PrettyDialogCallback() {
                            @Override
                            public void onClick() {
                                // Do what you gotta do
                            }
                        }
                )
                .addButton(
                        "Cancel",
                        R.color.pdlg_color_white,
                        R.color.pdlg_color_red,
                        new PrettyDialogCallback() {
                            @Override
                            public void onClick() {
                                // Dismiss
                            }
                        }
                )
                .addButton(
                        "Option 3",
                        R.color.pdlg_color_black,
                        R.color.pdlg_color_gray,
                        new PrettyDialogCallback() {
                            @Override
                            public void onClick() {
                                Toast.makeText(MainActivity.this, "I Do Nothing :)", Toast.LENGTH_SHORT).show();

                            }
                        }
                )
                .setSound(R.raw.ringtone)
                .setTitle("Do you agree?")
                .setTitleColor(R.color.pdlg_color_blue)
                .setAnimationEnabled(true)
                .setMessage("By agreeing to our terms and conditions, you agree to our terms and conditions.")
                .setMessageColor(R.color.pdlg_color_gray)
                .setTypeface(Typeface.createFromAsset(getResources().getAssets(),"myfont.ttf"));
```
