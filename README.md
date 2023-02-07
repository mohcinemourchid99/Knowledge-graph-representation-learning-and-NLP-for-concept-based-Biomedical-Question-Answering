# Knowledge-graph-representation-learning-and-NLP-for-concept-based-Biomedical-Question-Answering
 ##  Contributors
 1) OULDBOUYA Ziad
 2) MOURCHID Mohcine 
 
 # Supervisor
 Fahd Kalloubi

   	Knowledge graph representation learning 
	and NLP for concept-based Biomedical 
	Question/Answering
 
 
 ## Workflow
![Alt text](C:/Users/Mohcine/Downloads/White Simple Photocentric Zoom Virtual Background.png)
 - [x] Solving Poisson equation using Finite difference and Jacobi's iterative solver
- [ ] Solving the advection diffusion equation using Finite difference
- [x] Coupling both to solve the NS equation (already done using Numba and Pyccel)
- [x] Compare the numerical result with the serial code
- [x] Show the execution time for the parallel code using 1, 2, 4 ... processes
- [x] Compare the results with the OpenMP implementation.

 ## Strategies
  - Split the grid using MPI Cart
 - Create the derivative type to send halo information to the neighbor processes
 - Each process will solve the equation using its local grid, and send/recv the missed information (halo information) to compute the new solution on the whole grid
 
## Solving 2D Poisson equation

    - Delta u = f(x,y)= 2*(x*x-x+y*y -y)
    - u equal 0 on the boudaries
    - The exact solution is u = x*y*(x-1)*(y-1)
 
    - The u value is :
            coef(1) = (0.5*hx*hx*hy*hy)/(hx*hx+hy*hy)
            coef(2) = 1/(hx*hx)
            coef(3) = 1/(hy*hy)
 
     u(i,j)(n+1)= coef(1) * (  coef(2)*(u(i+1,j)+u(i-1,j)) + coef(3)*(u(i,j+1)
        +u(i,j-1))-f(i,j))

 *   ntx and nty are the total number of interior points along x and y, respectivly.
 
 *   hx is the grid spacing along x and hy is the grid spacing along y.
 *    hx = 1./(ntx+1)
 *    hy = 1./(nty+1)
 ###   On each process, we need to:
   1) Split up the domain
   2) Find our 4 neighbors
   3) Exchange the interface points
   4) Calculate u

