FROM jupyter/scipy-notebook:x86_64-python-3.11.6

# Enable sudo for the default user (jovyan) inside the container
ENV GRANT_SUDO yes

# Install mamba, a faster package manager based on conda, from conda-forge
RUN conda install mamba -c conda-forge

# Switch to root user to install system-level dependencies
USER root

# Install necessary libraries for geospatial data processing and scientific computing
RUN apt-get update && apt-get install -y \
    software-properties-common \
    gdal-bin \
    python3-gdal \
    libproj-dev \
    proj-data \
    proj-bin \
    libgeos-dev \
    libspatialindex-dev \
    libgdal-dev \
    libblas-dev \
    liblapack-dev \
    libatlas-base-dev \
    gfortran \
    libhdf5-serial-dev \
    libnetcdf-dev \
    libopenblas-dev \
    libopenmpi-dev \
    libpng-dev \
    libz-dev \
    && add-apt-repository ppa:ubuntugis/ppa \
    && apt-get update \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Update all conda packages to their latest versions using mamba

RUN mamba update --quiet --yes --all

# Install data science and machine learning libraries using mamba for performance

RUN mamba install --quiet --yes \
    'cudatoolkit' \ 
    'mkl' \ 
    'pytorch-cpu' \ 
    'torchvision-cpu' \ 
    'gdal' \ 
    -c pytorch -c conda-forge -c anaconda

# Upgrade pip to the latest version

RUN pip install pip --upgrade

# Install cloud storage libraries for interacting with major cloud providers (AWS, Google, Azure, IBM, etc.)

RUN pip install --user  \
    'boto3' \
    'awscli' \
    'google-cloud-storage' \
    'google-cloud-bigquery' \
    'google-cloud-pubsub' \
    'google-auth' \
    'azure-storage-blob' \
    'azure-cosmos' \
    'azure-servicebus' \
    'azure-identity' \
    'ibm-cos-sdk' \
    'ibm-watson' \
    'oci' \
    'python-digitalocean' \
    'heroku3' \
    'aliyun-python-sdk-core'

# Install data visualization libraries

RUN pip install --user \
    'pandas-profiling' \
    'sweetviz' \ 
    'graphviz' \
    'bokeh' \
    'altair' \
    'plotnine' \  
    'pygal' \    
    'dash' \
    'holoviews' \
    'hvplot' \
    'plotly' \
    'convertdate' \
    'holidays' \
    'workalendar' \
    'lunarcalendar' \
    'thinc' \
    'torchmetrics' \
    'pytorch_lightning' \
    'torch-summary'

# Install optimization libraries

RUN pip install --user \
    'cvxpy' \
    'pyomo' \
    'optuna' \
    'hyperopt' \    
    'deap' \
    'pygad' \
    'geneticalgorithm' \
    'scikit-optimize' \
    'GPyOpt' \
    'bayesian-optimization' \
    'nlopt' \
    'pyswarm' \ 
    'pyswarms' \
    'simanneal' \
    'cvxopt' \
    'pulp' \
    'platypus' \
    'pymoo' \
    'nevergrad' \
    'cma' 

# Install Hyperopt-Sklearn for hyperparameter optimization with scikit-learn

RUN pip install git+https://github.com/hyperopt/hyperopt-sklearn

# Install machine learning and model interpretability tools

RUN pip install --user \
    'scikit-learn' \
    'xgboost' \
    'lightgbm' \
    'catboost' \
    'shap' \ 
    'eli5' \
    'lime' \
    'pdpbox' \
    'imbalanced-learn' \ 
    'handcalcs' \
    'tqdm' \ 
    'wandb' \ 
    'jupyter_http_over_ws' \ 
    'jupyter_contrib_nbextensions' \
    'jupyter_nbextensions_configurator'


# Install computer vision libraries

RUN pip install --user \
    'opencv-python' \
    'ffmpeg-python' \
    'scikit-image' \
    'scikit-video' \
    'imageio' \
    'Pillow' \
    'mahotas' \
    'kornia' \
    'imgaug' \
    'albumentations' \
    'pytesseract' \
    'easyocr' \
    'calamari-ocr' \
    'vidgear'

# Install time series analysis libraries

RUN pip install --user \
    'pmdarima' \
    'darts' \
    'tslearn' \
    'tsfresh' \
    'tsai' \
    'deep-time-series' \
    'tsaug' \
    'prophet' \
    'gluonts'



# Install natural language processing (NLP) libraries

RUN pip install --user \
    'nltk' \
    'gensim' \
    'jsonlines' \
    'huggingface_hub' \
    'transformers' \
    'accelerate' \
    'transformers[sentencepiece]' \
    'openai' \
    'openai-whisper' \
    'sentence-transformers' \
    'faiss-cpu'

# Download SpaCy language models for various use cases (large, medium, small, transformer-based)

RUN python3 -m spacy download en_core_web_lg
RUN python3 -m spacy download en_core_web_md
RUN python3 -m spacy download en_core_web_sm
RUN python3 -m spacy download en_core_web_trf

# Install geospatial libraries

RUN pip install --user \
    --extra-index-url 'https://artifactory.vgt.vito.be/artifactory/api/pypi/python-packages/simple' \
    'networkx' \
    'rtree' \
    'geoindex-rs' \
    'osmnx' \
    'overpass' \
    'osmnet' \
    'osmapi' \
    'osm2gpd' \
    'osm2geojson' \
    'cartopy' \
    'gdal' \
    'geoplot' \
    'geojson' \
    'geoviews' \
    'geopy' \
    'chord' \
    'folium' \
    'leafmap' \
    'rasterio' \
    'netCDF4' \
    'rioxarray' \
    'xarray' \
    'geopandas' \
    'rasterstats' \
    'pyproj' \
    'pycrs' \
    'pyshp' \
    'pysal' \
    'shapely' \
    'fiona' \
    'copernicusmarine' \
    'cdsapi' \
    'terracatalogueclient' \
    'blue-geo' \
    'hestia-earth-earth-engine' \
    'geemap' \
    'earthengine-api' \
    'xee' \
    'movingpandas' \
    'segment-geospatial'
    
# Install audio processing libraries

RUN pip install --user \
    'librosa' \
    'pydub' \
    'soundfile' \
    'python_speech_features' \
    'pywavelets' \
    'audioread'

# Install bioinformatics libraries

RUN pip install --user \
    'biopython' \
    'pysam' \
    'dendropy' \
    'ete3' \
    'goatools' \
    'bcbio-gff' \
    'pybedtools' \
    'pyfaidx' \
    'deeptools' \
    'scanpy' \
    'anndata' 

# Change ownership of the home directory to the default user

USER root
RUN chown -R ${NB_UID} ${HOME}

# Switch back to the default user
USER $NB_UID
