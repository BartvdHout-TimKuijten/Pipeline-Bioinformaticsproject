This directory contains the commands used to install software using conda

Hamronize install

'''
conda create --name hamronization --channel conda-forge --channel bioconda --channel defaults hamronization
'''

Abricate install

'''
conda create -n abricate
conda activate abricate
conda install -c conda-forge -c bioconda -c defaults abricate
'''

StarAMR install

'''
conda create -n staramr
conda activate staramr
conda install -c bioconda staramr
staramr db build -h
'''

AntiSMASH install

'''
conda create -n antismash python=2.7
conda activate antismash
conda config --add channels defaultsconda config --add channels biocondaconda config --add channels conda-forge
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
conda install -c bioconda antismash
'''

planemo install

'''
conda create -n planemo
conda activate planemo
conda install -c bioconda planemo
'''
