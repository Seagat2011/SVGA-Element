# SVGA-Element
Scale-invariant (Fractal) Vector Graphics Array Elements for IMAX video games

## Example  

```js
//AVAILABLE NOMENCLATURES  
1a. class[ "property.attribute[.dimensional_units .. (optional)].number_system" ] = value;  
    .  
    .  

1b. class.Update({  
     "property.attribute[.dimensional_units .. (optional)].number_system":callback,  
      .  
      .  
   })  

2. class.APIs.property.attribute[.dimensional_units .. (optional)].number_system // for documentation purposes //  


//OPTION 1:Performance  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();  
fertileEarth["soil.humidity.percent.float"] = 80;  
fertileEarth["soil.ph.float"] = 7.0;  
fertileEarth["light.direction.cm.vector._3.float"] = [0,2,4];  
fertileEarth.Init();  

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();  
bladeGrass["wind.direction.cm.vector._3.float"] = [0,3,0];  
bladeGrass["wind.velocity.mph.vector._3.float"] = 12;  
bladeGrass["light.direction.cm.vector._3.float"] = 1;  
bladeGrass["light.distance.cm.vector._3.float"] = 2;  
bladeGrass["light.intensity.lumins.vector._3.float"] = 2;  
bladeGrass["soil.dampness.float"] = 1;  
bladeGrass["soil.humidity.percent.float"] = 1;  
bladeGrass["soil.ph.float"] = 2;
bladeGrass.Init();  


//OPTION 2:Direct Init  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();  
fertileEarth.Init({  
  "soil.humidity.percent.float":80,  
  "soil.ph.float":7.0,  
  "light.direction.cm.vector._3.float":[0,2,4]  
});

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();  
bladeGrass.Init({   
  "wind.direction.cm.vector._3.float":[0,3,0],  
  "wind.velocity.mph.vector._3.float":12,  
  "light.direction.cm.vector._3.float":1,  
  "light.distance.cm.vector._3.float":2,  
  "light.intensity.lumins.vector._3.float":2,  
  "soil.dampness.float":1,  
  "soil.humidity.percent.float":1,  
  "soil.ph.float":2  
});  


//OPTION 3:Add listeners  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();   
fertileEarth["soil.humidity.percent.float"] = 80;  
fertileEarth["soil.ph.float"] = 7.0;  
fertileEarth["light.direction.cm.vector._3.float"] = [0,2,4];  
fertileEarth.Init()
fertileEarth.Update({  
  "soil.humidity.percent.float":soil_humidity_callback_func,  
  "soil.ph.float":soil_ph_callback_func,  
  "light.direction.cm.vector._3.float":light_direction_callback_func,  
  "surface.grass.kentucky.nearest.neighbor.mm.float":surface_grass_callback_func,  
  "surface.soil.fertile.nearest.neighbor.cm.float":surface_soil_callback_func  
});  

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();   
bladeGrass["wind.direction.cm.vector._3.float"] = [0,3,0];  
bladeGrass["wind.velocity.mph.vector._3.float"] = 12;  
bladeGrass["light.direction.cm.vector._3.float"] = 1;  
bladeGrass["light.distance.cm.vector._3.float"] = 2;  
bladeGrass["light.intensity.lumins.vector._3.float"] = 2;  
bladeGrass["soil.dampness.float"] = 1;  
bladeGrass["soil.humidity.percent.float"] = 1;  
bladeGrass["soil.ph.float"] = 2;
bladeGrass.Init();  
bladeGrass.Update({   
  "wind.direction.cm.vector._3.float":wind_direction_callback_func,  
  "wind.velocity.mph.vector._3.float":wind_velocity_callback_func,  
  "light.direction.cm.vector._3.float":light_direction_callback_func,  
  "light.distance.cm.vector._3.float":light_distance_callback_func,  
  "light.intensity.lumins.vector._3.float":light_intensity_callback_func,  
  "soil.dampness.float":soil_dampness_callback_func,  
  "soil.humidity.percent.float":soil_humidty_callback_func,  
  "soil.ph.float":soil_ph_callback_func,  
  "surface.grass.kentucky.nearest.neighbor.mm.float":surface_grass_callback_func,  
  "surface.soil.fertile.nearest.neighbor.cm.float":surface_soil_callback_func  
});


//OPTION 4:Documentation Purposes
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();   
console.log( fertileEarth.soil.humidity.percent.float );  // true
console.log( fertileEarth.soil.ph.float ); // true ); // true
console.log( fertileEarth.light.direction.cm.vector._3.float ); // true

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();   
console.log( bladeGrass.wind.direction.cm.vector._3.float ); // true
console.log( bladeGrass.wind.velocity.mph.vector._3.float ); // true
console.log( bladeGrass.light.direction.cm.vector._3.float ); // true
console.log( bladeGrass.light.distance.cm.vector._3.float ); // true
console.log( bladeGrass.light.intensity.lumins.vector._3.float ); // true
console.log( bladeGrass.soil.dampness.float ); // true
console.log( bladeGrass.soil.humidity.percent.float ); // true
console.log( bladeGrass.soil.ph.millimeters ); // Error;
console.log( JSON.stringify( bladeGrass.soil.ph ) ); // { float:true }
```  


NOTES   

-n-elements require log2N channels of communication per commit-frame (what about logFactorialN)  
-messages are only posted to Listeners  
