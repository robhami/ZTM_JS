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

Can also add medium columns with different numbers that only kick in when window size is medium. Then go to small number of lines when window is small. 
```
<div class="row">
			<div class="col col-sm-6 col-md-12">
				col col-sm-6 col-md-12
			</div>
			<div class="col col-sm-3 col-md-6">
				col col-sm-6 col-md-6
			</div>
			<div class="col col-sm-4 col-md-6">
				col col-sm-6 col-md-6
			</div>
		</div>

		
