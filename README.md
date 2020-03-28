# tolosat_grav_payload
This is the repository for the software tools developped by the gravimetry payload of the TOLOSAT CubeSat.  

You can find the 'data' directory with the coefficients files and the trajectory files at:  
https://drive.google.com/drive/folders/19jqZdLf2ABAerFzBV8e-6N0IGVGUOotc
It must be plqced in the same directory as 'source', which contains all the precious scripts.

Main Information: 

     This tool has been developped to strengthen our claims, here at the 
     TOLOSAT Gravimetry Payload. I have late-night-baptized this tool:
         
                                     "Grav Harm 3"
                            "Gravitational Harmonics 3"
     
    for it is the third attemp at writing this tool from the ground up.
    Any other name ideas are gladly welcome, X.
    
    
    Change your variables, do your maths, and do your science. 
    Let's go to space, y'all    
    
    Process : 
    1.  Generate the acceleration values (from orbit data or raw simulation)
            using GH_generate
    2.  Solve for the coefficients using the functions in this script
            using GH_solve
    3.  Generate a Geoid map from solved coefficients
            using GH_displayCoef
    4.  Compare Geoids or coefficients
            using GH_displayCoef
    5.  Plot Satellite positions and accelerations in space
            using GH_displaySat



# =============================================================================
 Additionnal information:
     
     This tool was originally developped in Spyder 3, for python3. 
          
     This python tool uses the spherical coordinates system : 
         r = radius in km ; [0, np.inf()]
         theta = inclination from the z axis in radians; [0, pi]
         phi = rotation around the z axis in radians; [0, 2*pi]
     
         They must be adapted to lat/lon coordinates by adding : 
             -pi/2 to theta
             -pi to phi
     
         Their equivalent in the cartesian coordinates is : sph2cart(r,theta,phi):
             x=r*np.sin(theta)*np.cos(phi)
             y=r*np.sin(theta)*np.sin(phi)
             z=r*np.cos(theta)

    The main source for the mathematics involved in this code is : 
        "Definition of Functionals of the Geopotential 
        and Their Calculation from Spherical Harmonic Models"
        by Franz Barthelmes
        for ICGEM
        Revision: jan. 2013
        Will be refered to as "GFZ" in al scripts in this tool.
    
    The original coordinates used so far are rendered sing NASA's free open
        source GMAT software. Ask folks from the mission analysis payload to
        show you how it works.    
     
