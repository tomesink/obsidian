
1. Hide the native Webflow arrows (don't delete, just hide)
2. Build custom arrows
3. Give arrows the classes of .next-button and .back-button
4. Add the id of `#flowbaseSlider` to the slider component
5. Add the script before the body tag in the page settings:

```javascript
<script>
var Webflow = Webflow || [];
Webflow.push(function() {
	var l = $('#flowbaseSlider .w-slider-arrow-left');
	var r = $('#flowbaseSlider .w-slider-arrow-right');
	$('#flowbaseSlider')
		.on('click', '.back-button', function() {
			l.trigger('tap');
		})
		.on('click', '.next-button', function() {
			r.trigger('tap');
		});
});
</script>
```