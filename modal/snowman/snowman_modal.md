# "Modal (Pop-up Window)": Snowman (1.3.0)

## Summary
This example uses the jQuery *click()* and *show()/hide()* functions to watch for the user clicking on a button (to open) or "X" (to close). Additional CSS rules are used to create the effect of having the content 'behind' the modal be darkned and unusable until the modal itself is closed.


## Live Example

<section>
<iframe src="snowman_modal_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_modal_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Modal

:: UserScript[script]
$(function(){

        // When the user clicks the button, open the modal 
        $("#myBtn").click(function() {
              $("#myModal").show();
        });

        // When the user clicks on <span> (x), close the modal
        $(".close").click(function() {
              $("#myModal").hide();
        });

});


:: UserStylesheet[stylesheet]
/* The Modal (background) */
.modal {
    display: none; /* Hidden by default */
    position: fixed; /* Stay in place */
    z-index: 1; /* Sit on top */
    padding-top: 100px; /* Location of the box */
    left: 0;
    top: 0;
    width: 100%; /* Full width */
    height: 100%; /* Full height */
    overflow: auto; /* Enable scroll if needed */
    background-color: rgb(0,0,0); /* Fallback color */
    background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content */
.modal-content {
    background-color: #fefefe;
    margin: auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
}

/* The Close Button */
.close {
    color: #aaaaaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: #000;
    text-decoration: none;
    cursor: pointer;
}


:: Start
<button id="myBtn">Open Modal</button>

<div id="myModal" class="modal">
  <div class="modal-content">
    <span class="close">×</span>
    <p>Example text in the modal</p>
  </div>
</div>

```

Download: <a href="snowman_modal_twee.txt" target="_blank">Twee Code</a>
