# MRI_Phantom

Generation of simple magnetic resonance imaging (MRI) using a Shepp-Logan Digital Phantom
Use Python
You can use functions and libraries for generating and presenting graphs and images
Background: Among the most famous digital phantoms are based on a 2D one originally introduced by Shepp and Logan in 1974 (L. A. Shepp and B. F. Logan, "The Fourier reconstruction of a head section," IEEE Transactions on Nuclear Science, vol. NS-21, pp. 21- 43, 1974) and later extended to 3D by Shepp (L. A. Shepp, "Computerized tomography and nuclear magnetic resonance," J Comput Assist Tomogr, vol. 4, pp. 94-107, 1980.). Those phantoms were originally made to study reconstruction algorithms in Computed Tomography (CT) and then extended to MRI.

This figure shows a standard Shepp Logan phantom generated in Matlab with the phantom function. In Matlab the code we used was:
>> ph = phantom(1024);
>> figure, imshow(ph);
The purpose of this assignment is to familiarize yourself with the source code of a 2D Shepp- Logan digital phantom and make it appropriate for Magnetic Resonance Imaging.
You have three tasks

1.	Modify the Shepp-Logan phantom: Start with the source code that generates this phantom in Matlab or Python. Modify the default parameters that define the ellipses so that:
•	There are no overlapping structures, as example: make structure (1) smaller, move structure
(2) lower.
•	make the three structures in (3) to be circles and not overlapping,
•	Add the display of the phantom.
Report the code as you modified it and an outcome (like figure above – without the numbers!
 
2.	A question: How many different compartments you have? Assume that tissue in (4) is the same with tissue in (2)

3.	Create a simple virtual MRI scanner: Let’s further modify your code to create a simple patient-mimicking digital phantom for use in generating MRI. We will assume that your virtual scanner simulates a simple MRI machine that collects only one type of MRI images that the signal intensity (SI) acquired from a voxel is given by the formula:
SI = A * (1 - exp(-TR / T1)) * exp(-TE / T2)
A = a number that depends on the amount of water in this voxel
T1 = is a property of tissue in the voxel (longitudinal relaxation time) T2 = is a property of the tissue in the voxel (transverse relaxation time)
TR = is a parameter that the operator of the system selects (the repetition time) TE = is a parameter that the operator of the system selects (the echo time)
Therefore we must assign different T1 and T2 values to the different tissues! If N is the number of different compartments then use these formulas
T1 = 50 + (j-1)*250 j = 1 to N T2 = 10 + (j-1)*50 j = 1 to N
Where j is a compartment form the figure.

Assign an A to each compartment between 0.0 and 1.0 …
Question: which compartments are those with A = 0.0 and 1.0?
So, do you want to update the answer to the previous question of “how many compartments has your phantom?”

3.1	Physical Properties Maps: Generate and present the A-map, T1-map and T2-map of your phantom.
3.2	Effect of User-selected Acquisition parameters:
In a table like this one below report the corresponding values, T1, T2,

Structure index	A	T1	T2	SI1	SI2	SI3	SI4
1							
2							
…							
N							
Calculate the SI above for the four cases of acquisition parameters

	TR	TE
SI1	50	10
SI2	250	10
SI3	1000	10
SI4	2500	10
 
3.3	Report the four generated MRI next to each other. What is the effect of the changing the TR?
3.4	Effect of Acquisition Parameters on contrast: Plot SI versus TR and TE What is the role of each operator selectable parameter to the SI?
When you change the TR which physical parameter’s contribution to contrast is explored? Similarly, when you change the TR which physical parameter’s contribution to contrast is explored?
![image](https://github.com/FahadKhalid1/MRI_Phantom/assets/22212834/3aea6b5b-fb27-4f5e-b8a2-18caae458c7f)
