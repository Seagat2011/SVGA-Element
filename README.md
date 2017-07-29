# SVGA-Element
Scale-invariant (Fractal) Vector Graphics Array Elements for IMAX video games

## Example  

```js
//AVAILABLE NOMENCLATURES  
1a. class[ "property.attribute[.dimensional_units .. (optional)].number_system" ] = value;  
    .  
    .  

1b. class.Update({  
     "property.attribute[.dimensional_units .. (optional)].number_system" : value,  
      .  
      .  
   })  

2. class.APIs.property.attribute[.dimensional_units .. (optional)].number_system // for documentation purposes //  


//OPTION 1:Performance  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();  
fertileEarth["soil.humidity.percent.float"] = 80;  
fertileEarth["soil.ph.float"] = 7.0;  
fertileEarth["light.direction.cm.vector.3.float"] = [0,2,4];  
fertileEarth.Init();  

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();  
bladeGrass["wind.direction.cm.vector.3.float"] = [0,3,0];  
bladeGrass["wind.velocity.mph.vector.3.float"] = 12;  
bladeGrass["light.direction.cm.vector.3.float"] = 1;  
bladeGrass["light.distance.cm.vector.3.float"] = 2;  
bladeGrass["light.intensity.lumins.vector.3.float"] = 2;  
bladeGrass["soil.dampness.float"] = 1;  
bladeGrass["soil.humidity.percent.float"] = 1;  
bladeGrass["soil.ph.float"] = 2;
bladeGrass.Init();  


//OPTION 2:Direct Initialize  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();  
fertileEarth.Init({  
  "soil.humidity.percent.float":80,  
  "soil.ph.float":7.0,  
  "light.direction.cm.vector.3.float":[0,2,4]  
});

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();  
bladeGrass.Init({   
  "wind.direction.cm.vector.3.float":[0,3,0],  
  "wind.velocity.mph.vector.3.float":12,  
  "light.direction.cm.vector.3.float":1,  
  "light.distance.cm.vector.3.float":2,  
  "light.intensity.lumins.vector.3.float":2,  
  "soil.dampness.float":1,  
  "soil.humidity.percent.float":1,  
  "soil.ph.float":2  
});  


//OPTION 3:Add listeners  
var fertileEarth = new Object["SVGA-element"].SURFACE.SOIL.FERTILE();   
fertileEarth["soil.humidity.percent.float"] = 80;  
fertileEarth["soil.ph.float"] = 7.0;  
fertileEarth["light.direction.cm.vector.3.float"] = [0,2,4];  
fertileEarth.Init()
fertileEarth.Update({  
  "soil.humidity.percent.float",  
  "soil.ph.float",  
  "light.direction.cm.vector.3.float",  
  "surface.grass.kentucky.nearest.neighbor.mm.float",  
  "surface.soil.fertile.nearest.neighbor.cm.float"  
});  

var bladeGrass = new Object["SVGA-element"].SURFACE.GRASS.KENTUCKY();   
bladeGrass["wind.direction.cm.vector.3.float"] = [0,3,0];  
bladeGrass["wind.velocity.mph.vector.3.float"] = 12;  
bladeGrass["light.direction.cm.vector.3.float"] = 1;  
bladeGrass["light.distance.cm.vector.3.float"] = 2;  
bladeGrass["light.intensity.lumins.vector.3.float"] = 2;  
bladeGrass["soil.dampness.float"] = 1;  
bladeGrass["soil.humidity.percent.float"] = 1;  
bladeGrass["soil.ph.float"] = 2;
bladeGrass.Init();  
bladeGrass.Update({   
  "wind.direction.cm.vector.3.float",  
  "wind.velocity.mph.vector.3.float",  
  "light.direction.cm.vector.3.float",  
  "light.distance.cm.vector.3.float",  
  "light.intensity.lumins.vector.3.float",  
  "soil.dampness.float",  
  "soil.humidity.percent.float",  
  "soil.ph.float",  
  "surface.grass.kentucky.nearest.neighbor.mm.float",  
  "surface.soil.fertile.nearest.neighbor.cm.float"  
});
```  


NOTES   

-n-elements require log2N channels of communication per commit-frame (what about logFactorialN)  
-messages are only posted to Listeners  
