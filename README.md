# coastline-modelingindian-ocean-coastline
Create a clean Python environment for your project:bashconda create -n transolver_coast python=3.10
conda activate transolver_coast
Use code with caution.Step 2: Install PyTorch (CPU Mode)Since the Intel Mac cannot leverage standard CUDA acceleration, install the CPU-optimized version of PyTorch:bashconda install pytorch torchvision torchaudio cpuonly -c pytorch
Use code with caution.Step 3: Clone the Repository & Install DependenciesClone the core code and install standard scientific computing libraries for processing the geographic meshes:bashgit clone https://github.com
cd Transolver_plus
pip install numpy pandas matplotlib scipy scikit-learn
Use code with caution.(Note: Because you are on a CPU, you can bypass installing triton or any custom .cu CUDA extensions found in the script setups).Step 4: Set up Data Handling for Kenya's CoastlineBefore feeding data into Transolver++, you need to transform the GIS datasets into an unstructured point cloud/mesh format:Install geospatial packages to handle regional boundaries:bashpip install geopandas shapely
Use code with caution.Download your base spatial vectors from the Kenya Coastal Data - RCoE Geoportal.Sample the shoreline vector into a series of X, Y coordinates (and Z for elevation if you have a Digital Elevation Model). This point cloud will match the (Batch, N, Channel) dimensions that the Physics-Attention layers expect.
