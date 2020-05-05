# ZeroToMastery Bootstrap Grid



Bootstrap has grid system broken into 12 column widths. 
So in below code first column uses 6 lines (columns) and second uses 3 & third uses 3. Therefore all 12 spaces are used. 
If "Extra" is omitted a space of 3 would exist.

```
<div class="container">
		<div class="row">
			<div class="col col-sm-6">
				1 of 2
			</div>
			<div class="col col-sm-3">
				2 of 2
			</div>
      <div class="col col-sm-3">
				Extra
			</div>
		</div>
</div>
```

If exceeds 12 col that exceeds goes to next level. 

```
<div class="container">
		<div class="row">
			<div class="col col-sm-6">
				1 of 2
			</div>
			<div class="col col-sm-3">
				2 of 2
			</div>
      <div class="col col-sm-4">
				Extra
			</div>
		</div>
</div>
```


		
