# "Typewriter Effect": Harlowe (v2.0)

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In Harlowe, this is achieved using the *[(live:)](https://twine2.neocities.org/#macro_live)* macro for delayed showing and the *[(append:)](https://twine2.neocities.org/#macro_append)* macro to append text to a hook.

## Live Example

<section>
<iframe src="harlowe_typewriter_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_typewriter_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Typewriter Effect in Harlowe

:: Start
<!-- Set the text to show -->
(set: $typewriterText to "Hello, world!")
<!-- Display (call) the Typewriter passage -->
(display: "Typewriter")

:: Typewriter
{
	<!-- Create a variable to track the position within the $typewriterText string -->
	(set: $typewriterPos to 1)
	
	<!-- Create a hook to hold the typed text -->
	|typewriterOutput>[]
	
	<!-- Set a delay of 0.2 seconds per loop -->
	(live: 20ms)[

		<!-- Add the next character to the hook -->
		(append: ?typewriterOutput)[(print: $typewriterText's $typewriterPos)]
		
		<!-- Update the position -->
		(set: $typewriterPos to it + 1)
		
		<!-- If it's gone past the end, stop -->
		(if: $typewriterPos is $typewriterText's length + 1)[
			(stop:)
		]
	]
}

```

Download: <a href="harlowe_typewriter_twee.txt" target="_blank">Twee Code</a>

## Notes

 * This does not allow you to use Harlowe code within the `$typewriterText` string - it will all be printed as-is.

 * You can only use `(display: "Typewriter")` once per passage.
