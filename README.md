# Gif Search

* GIPHY API to make a dynamic web page that populates with gifs of your choice.

## target user

* People who wants to look at gif all day
* People who is tired from work and chill at their own time

## tools used
* Javascript
* Jquery
* giphy API client call using .Ajax "GET" method
* bootstrap for frame work

## Set up
* there are some buttons for animal gifs like dog and cat
* if one wants to add more image catagory, one can do so by adding new button on search gif input box
  * blue buttons give user output
  * red button clears result or buttons
  * green button populates button

## output
* 10 gif images come in as output once the button is press with catagroy name.
* images come in with no animation.
* once the images are pressed the images come to life (animation).

### .ajax client side call
```javascript
var queryURL = "https://api.giphy.com/v1/gifs/search?q=" +
        image + "&api_key=XXX";

      $.ajax({
          url: queryURL,
          method: "GET"
        })
        .then(function(response) {
          console.log(response);
         });
          
 ```
### click function to change still image to gif image
```javascript
var gifImage = $("<img>");
            gifImage.attr("src", results[i].images.fixed_height_still.url);
            gifImage.attr("data-still", results[i].images.fixed_height_still.url);
            gifImage.attr("data-animate", results[i].images.fixed_height.url);
            gifImage.attr("data-state", "still");
            
$(".gif").on("click", function() {
            console.log($(this).attr("data-state"));
            if ($(this).attr("data-state")=="still") {
              $(this).attr("data-state", "animate");
              var newSrc=$(this).attr("data-animate");
              $(this).attr("src", newSrc);
            }else{
              $(this).attr("data-state", "still");
              // var newSrc=$(this).attr("data-still");
              $(this).attr("src", $(this).attr("data-still"));
            }
          });
  ```
  
