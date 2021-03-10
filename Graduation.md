# Architectural lessons from Topology Optimization

This page shows my work for my graduation, where I researched the topic of Topology Optimization and its possible implementations in architecture. This research was performed under the supervision of P. Nourian (_Faculty of Architecture and the Built Environment_) and M. Langelaar (_Faculty of 3Me_). A link to my work in the TU Delft repository can be found [here](http://resolver.tudelft.nl/uuid:5dc60528-701c-496c-90a2-a804d7a7aada).

This page will summarize my process and the results of this research. 

### Topology Optimization

The main idea behind topology optimization is to calculate what voxels (or pixels) in an element are important for the stiffness and what voxels can be removed. Because there is no preconceived shape, topology optimization can create innovative and high-performance shapes (Liu & Tovar, 2014). A system of voxels is created that will act as the design space and certain constraints will act as the loads and supports of the system. Usually, this process is used in mechanical or aerospace engineering, as it creates shapes with relatively high strength and relatively low volume.

### Previous research

In topology optimization, first Finite Element Analysis is performed on the system and the displacements of all the elements are calculated. To simplify the system, assumed is that the size of each voxel is 1 and that the material behaves identically in all directions. The displacements are needed to optimize the system, as the goal is to maximize the stiffness. In this optimization problem, instead of maximizing the stiffness, the compliance is minimized. Compliance is defined as how much the system can move and is written as in formula (1):

![Compliance](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_1.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_1.png)

Often Gradient Descent is used to find the minimal value and to use that, the derivative of the compliance, see formula (2) is calculated. Using the derivative the optimizer can choose the most important elements for the system and thus optimizing the strength. 

### Topology Optimization in Architecture

In my research, I wanted to find ways how the constraints could represent architectural systems. First, the algorithm was changed to work in 3D, following the paper of Deetman, 2019. Deetman changed the algorithm to work in 3D, generating a new stiffness-matrix and having a new system to count elements and Degrees Of Freedom. I translated Deetman's code to Python so that it could be implemented in Rhino (Rhino is needed so that node IDs could be generated for voids, supports and loads). This generated some nice shapes as follows:

![3D Results](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_2.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_2.png)

In architectural problems, some other problems arise, as in architectural problems most forces come from the geometry itself. Placing a voxel will not always improve the stiffness, as it can also generate new forces which decrease the stiffness. Density-dependent forces have to be added to the algorithm, which are new forces on nodes where the element around the nodes is existent. Formula (3) shows how this can be mathematically described using a sigmoid function. This doesn't seem to be hard, but the derivative also has to change. Previously the force was pre-set, but now the force is dependent on the density, the force should be included in the derivative. Now the derivative looks like the following:

![Selfweight](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_Self.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_Self.png)

Implementing this in the algorithm shows another problem, as the graph per element is no longer linear. This means that using Gradient Descent will no longer always give the minimum of the system. Another optimizer is used, called the Method of Moving Asymptotes.

Solving the system now still relies on a force, which is not always the case in architectural problems. Instead of forces in the system, the constraint in buildings is more that each void has a roof over itself. Or in other words; for each void, the sum of the elements in the column (above the void) should be larger than 1. In the system, we want to punish values that are not 1 or close to 1, so another sigmoid is implemented. In the algorithm at the end of each loop, if the sum is not larger than 1, all the elements above the void are set to a certain value. Self-weight will then make sure the roof is made and optimized.

![Selfweight results](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_3.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_3.png.png)

### Examples

Eventually, the algorithm was tested on several TOY problems. The algorithm had its flaws, but overall quite promising results were generated. Also, the Haus am Horn was used as an input, which was very interesting to see what happened. Domes were created over the rooms and also arcs were generated above the doors. 

![Selfweight results](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_4.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Graduation_4.png.png)

