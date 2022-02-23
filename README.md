## How-To-Set-Up-Toastr-For-Alert:

## About Package:

Follow below steps and add toastr in your laravel project for show your notification in message.

## Here you can find setup toastr for alert in your project.

## Step 1: 

## Add below links on your master layout head part;

```html
<head>
  {{-- toster --}}
	
    <link href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0-
     alpha/css/bootstrap.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

	<link rel="stylesheet" type="text/css"
     href="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/toastr.min.css">

    <script src="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/js/toastr.min.js"></script>
  {{-- /toster --}}
 </head>
 ```
 ## Step 2:
 
 ## Add below scripts on your master layout body part;
 
 ```html
 <script>
  @if(Session::has('message'))
  toastr.options =
  {
  	"closeButton" : true,
  	"progressBar" : true
  }
  		toastr.success("{{ session('message') }}");
  @endif

  @if(Session::has('error'))
  toastr.options =
  {
  	"closeButton" : true,
  	"progressBar" : true
  }
  		toastr.error("{{ session('error') }}");
  @endif

  @if(Session::has('info'))
  toastr.options =
  {
  	"closeButton" : true,
  	"progressBar" : true
  }
  		toastr.info("{{ session('info') }}");
  @endif

  @if(Session::has('warning'))
  toastr.options =
  {
  	"closeButton" : true,
  	"progressBar" : true
  }
  		toastr.warning("{{ session('warning') }}");
  @endif
</script>
```
## Step 3:

## Now go to your controller and add alert;

```php

return redirect()->back()->with('message', __('Brand has been deleted.'));
return redirect()->back()->with('error', __('Please try again.'));

```

