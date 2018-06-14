# Adding a new camera model = stereographic fisheye

**The mapping function : 2 * TAN (theta/2)** 

1. Definition of the _preconditioner_ i.e. the mapping from the angle to image position

    * the classical projection fn. u = PPx + F * X/Z
    * fisheye       projection fn. u = PPx + F * phi(theta) * u/r
                                    where if theta      = atan(r/F0) and
                                             phi(theta) = 2 tan(theta/2)
                                    then
                                         Prec = 2*tan( atan(r/F0)/2 ) / r
         
2. Defiinition of the functions that calcule the value of _Prec_ in `phgr_ebner_brown_dist.cpp`

    ..1. double `PrecStereographique(double x)`     computes the value with either of the below
    ..2. double `Std_PrecStereographique(double x)` computes exact value
    ..3. double `Dl_PrecStereographique(double x)`  computes value by Taylor expansion
 

2. Defiinition of the derivative functions after _Prec_ 

    1. double `Der_PrecStereographique(double x)`     
    2. double `Der_Std_PrecStereographique(double x)` 
    3. double `Der_Dl_PrecStereographique(double x)`

3. Definition of functions that will work on operators

    1. 
    `Fonc_Num PrecStereographique  (Fonc_Num f)
    {
     return Op_Un_Math::New
            (
                f,
                tab_PrecStereographique, //tabulated values of the function; not used for eisheye
                "PrecStereographique",   //name of the operator needed for auto cpp code generation 
                PrecStereographique,     //the value
                DPrecStereographique,    //the derivative
                NoValDeriv
            );
    }`

    2. The same for :

    `double Der_PrecStereographique(double x);
     double SqM2CRx_StereoG(double x);
     double Der_SqM2CRx_StereoG(double x);
     Fonc_Num Der_PrecStereographique(Fonc_Num f);
     Fonc_Num Der_SqM2CRx_StereoG(Fonc_Num f);`


4. Definition of the inverse function (when going from image toward 3D, i.e. C2M)

    `double Inv_PrecStereographique(double x);`


5. Defintion of the class that will gather the above and launch the automated derivative generation for the entire projectin function

    **class cFESterepGraphique** 

    1. Linking of `M2CRxSRx` with `PresStereographique`
    2. Linking of `C2MRxSRx` with `Inv_PrecStereographique`
