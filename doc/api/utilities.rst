.. currentmodule:: JuAFEM

.. _api-utilities:

*********
Utilities
*********

Plotting
--------

.. function:: eldraw2(ex, ey, [plotpar=[1,1,0], elnum=zeros(0)])

   .. Docstring generated from Julia source

   Draws the 2D mesh defined by ``ex``\ , ``ey``\ .

.. function:: eldisp2(ex, ey, ed, [plotpar=[1,1,0], sfac=1.0])

   .. Docstring generated from Julia source

   Draws the displaced 2D mesh defined by ``ex``\ , ``ey`` and the displacements given in ``ed``\ .

Solving system of equations
----------------------------

.. function:: solveq(K, f, bc, [symmetric=false]) -> a, fb

   .. Docstring generated from Julia source

   Solves the equation system Ka = f taking into account the Dirichlet boundary conditions in the matrix ``bc``\ . Returns the solution vector ``a`` and reaction forces ``fb`` If ``symmetric`` is set to ``true``\ , the matrix will be factorized with Cholesky factorization.

Coordinate extraction
----------------------

.. function:: extract(edof, a)

   .. Docstring generated from Julia source

   Extracts the element displacements from the global solution vector ``a`` given an ``edof`` matrix. This assumes all elements to have the same number of dofs.

.. function:: coordxtr(Edof,Coord,Dof,nen) -> Ex, Ey, Ez

   .. Docstring generated from Julia source

   Extracts the coordinates of the nodes of the elements.

   This function can be slow for large number of elements.

.. function:: topologyxtr(Edof,Coord,Dof,nen) -> topology

   .. Docstring generated from Julia source

   Extracts the connectivity matrix.

   This function can be slow for large number of elements.

Static condensation
-------------------

.. function:: statcon(K, f, cd) -> K_cond, f_cond

   .. Docstring generated from Julia source

   Condenses out the dofs given in cd from K and f.

Assembler
---------

.. function:: assemble(edof, a, Ke)

   .. Docstring generated from Julia source

   Assembles the element matrix ``Ke`` into ``a``\ .

