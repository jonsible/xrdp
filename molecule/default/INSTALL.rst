*******
Docker driver installation guide
*******

Requirements
============

* Docker Engine

Install
=======

Please refer to the `Virtual environment`_ documentation for installation best
practices. If not using a virtual environment, please consider passing the
widely recommended `'--user' flag`_ when invoking ``pip``.

.. _Virtual environment: https://virtualenv.pypa.io/en/latest/
.. _'--user' flag: https://packaging.python.org/tutorials/installing-packages/#installing-to-the-user-site

.. code-block:: bash

    # Set these variables according to your GCP setup
    GCE_CREDENTIALS_FILE=$HOME/.googlecloud/cred.json
    GCE_PROJECT_ID=projectid

    sudo apt-get -qq update
    curl https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-281.0.0-linux-x86_64.tar.gz | tar -xz -C /tmp
    /tmp/google-cloud-sdk/install.sh --quiet
    gcloud auth activate-service-account --key-file $GCE_CREDENTIALS_FILE
    gcloud config set project $GCE_PROJECT_ID
    sudo apt-get -y install python-pip libssl-dev git
    git clone https://github.com/kewlfft/ansible-aur.git ~/.ansible/plugins/modules/aur
    pip install --upgrade setuptools
    pip install ansible-lint
    pip install flake8
    pip install testinfra
    pip install molecule
    pip install molecule-gce
    pip install google-auth
    WDIR=$(pwd)
    cd /opt
    curl -L https://networkgenomics.com/try/mitogen-0.2.9.tar.gz | tar -xz
    cd $WDIR
    molecule test
