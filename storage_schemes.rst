Storage Schemes
===============

* seven sparse matrix types in scipy.sparse:

  1. csc_matrix: Compressed Sparse Column format
  2. csr_matrix: Compressed Sparse Row format
  3. bsr_matrix: Block Sparse Row format
  4. lil_matrix: List of Lists format
  5. dok_matrix: Dictionary of Keys format
  6. coo_matrix: COOrdinate format (aka IJV, triplet format)
  7. dia_matrix: DIAgonal format

* each suitable for some tasks
* many employ sparsetools C++ module by Nathan Bell
* assume the following is imported::
    
  >>> import numpy as np
  >>> import scipy.sparse as sps
  >>> import matplotlib.pyplot as plt

* **warning** for NumPy users:
  * the multiplication with '*' is the *matrix multiplication* (dot product)
  * not part of NumPy!
    * passing a sparse matrix object to NumPy functions expecting
      ndarray/matrix does not work

Common Methods
--------------

* all scipy.sparse classes are subclasses of :class:`spmatrix`
  * default implementation of arithmetic operations
    * always converts to CSR
    * subclasses override for efficiency
  * shape, data type set/get
  * nonzero indices
  * format conversion, interaction with NumPy (toarray(), todense())
  * ...
* attributes:
  * mtx.A - same as mtx.toarray()
  * mtx.T - transpose (same as mtx.transpose())
  * mtx.H - Hermitian (conjugate) transpose
  * mtx.real - real part of complex matrix
  * mtx.imag - imaginary part of complex matrix
  * mtx.size - the number of nonzeros (same as self.getnnz())
* data usually stored in NumPy arrays

.. toctree::
   :maxdepth: 2

   dia_matrix
   lil_matrix
   dok_matrix
   coo_matrix
   csr_matrix
   csc_matrix
   bsr_matrix