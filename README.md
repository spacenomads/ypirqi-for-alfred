# Ypirqi for Alfred

**Ypirqui for Alfred** is a simple workflow inspired by [Juan Alonso’s Ypirqui for Slack](https://github.com/juanalonso/ypirqui)

It is a quick shortcut to mock someone by copying a string and replace all the vowels with an `i`. Then you can paste it wherever you need it. **Use it wisely**.

## Requirements
Well, you need [Alfred app for Mac](https://www.alfredapp.com)

## Installation
Download the **.alfredworkflow** file, doubleclick it and you are ready to bring justice to your favourite messaging app or social network timeline!

## How to use it
<img src="https://www.dropbox.com/s/u7l3frs05llgrnb/launcher.png?dl=1" style="max-width:350px;display:block;margin: 0 auto;">

1. Wait for this someone to say something… 
2. Copy his text
3. Launch Alfred window
4. Type `ypq`
5. Now you have the text ready in you clipboard to paste it and answer him with style.

## The workflow
<img src="https://www.dropbox.com/s/79rf46g1al4gb3g/workflow.png?dl=1" style="max-width:450px;display:block;margin: 0 auto;">

This workflow uses 2 miniscripts to “capture” the clipborad content and replace the vowels. Then, an Alfred action puts the modified content back to the clipboard ;)

### “Capture” the clipboard content
```applescript
	on alfred_script(q)
		set {query} to the clipboard
	end alfred_script
```

### Replace the vowels
```javascript
	var query = "{query}";
	var ypirqi = function (string){
		var result = string;
		result =  result.replace(/([AEOUÁÉÓÚÀÈÒÙÄËÖÜ])/g,'I');
		result =  result.replace(/([aeouáéóúàèòùäëöü])/g,'i');
		return result;
	};
	ypirqi(query);
```

Yep, that’s all :)
