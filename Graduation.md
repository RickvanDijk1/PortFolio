#Architectural lessons from Topology Optimization

This page shows my work for my graduation, where I researched the topic of Topology Optimization and its possible implementations in architecture. This research was performed under the supervision of P. Nourian (_Faculty of Architecture and the Built Environment_) and M. Langelaar (_Faculty of 3Me_). A link to my work in the TU Delft repository can be found [here](http://resolver.tudelft.nl/uuid:5dc60528-701c-496c-90a2-a804d7a7aada).

This page will summarize my process and results of this research. 

## Topology Optimization

The main idea behind topology optimization is to calculate what voxels (or pixels) in an element are important for the stiffness and what voxels can be removed. Because there is no preconceived shape, topology optimization can create innovative and high-performance shapes (Liu & Tovar, 2014). A system of voxels is created that will act as the design space and certain constraints will act as the loads and supports of the system. Usually this process is used in mechanical or aerospace engineering, as it creates shapes with relative high strength and relative low volume.

# Previous research

In topology optimization, first Finite Element Analysis is performed on the system and the displacements of all the elements is calculated. To simplify the system, assumed is that the size of each voxel is 1 and that the material behaves identical in all directions. The displacements are needed to optimize the system, as the goal is to maximize the stiffness. In this optimization problem, in stead of maximizing the stiffness, the compliance is minimized. The compliance is defined as how much the system can move and is written as follows for each element:

C=UTKU + dfdx

Often Gradient Descent is used to find the minimal value and to use that, the derivative of the compliance, see formula (2) is calculated. Using the derivative the optimizer can choose the most important elements for the system and thus optimizing the strength. 

# Topology Optimization in Architecture

