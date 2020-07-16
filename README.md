# Patatap
Hi Everyone,

WARNING: The project in this section contains flashing colors.

If you're prone to photosensitive epilepsy (PSE) then please proceed with caution, or skip this section altogether.

In this project i have included Paperscript code internally in the HTML, using the script tag. 
If you try to include this script as an external .js file, it will break your app due to Cross Origin Resource Sharing.

In the refactor, the circles in the array are checked to see if their area is less than 1. If this condition returns true, then the circle is removed from the screen and from the array. See below:

function onFrame(event){
  for(var i = 0; i < circles.length; i++){
    circles[i].scale(0.9);
    circles[i].fillColor.hue += 1;
    if(circles[i].area < 1){
      circles[i].remove(); // remove the circle from the canvas
      circles.splice(i, 1); // remove the circle from the array
      console.log(circles);
    }
  }
}

Meanwhile, if you want to get rid of the Cross Origin errors in the console, you'll need to use live server with Visual Studio Code, see here for instructions; or you will need to run a local HTTP server from your project's directory and load the circles.html file from there.
