# Use the official Ubuntu 22.04 image
FROM ubuntu:22.04

# Install necessary dependencies, Java 8
RUN apt-get update && \ 
	apt-get install -y wget curl gnupg openjdk-8-jdk && \
	apt-get clean
	
# Install Miniconda
RUN wget -qO- https://repo.anaconda.com/miniconda/Moniconda3-latest-Linux-x86+64.sh && \
	bash /tmp/miniconda.sh -b -p /opt/miniconda && \
	rm /tmp/miniconda.sh && \
	/opt/miniconda/bin/conda clean -a && \
	ln -s /opt/miniconda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
	echo ". /opt/miniconda/etc/profile.d/conda.sh" >> ~/.bashrc && \
	echo "conda activate base" >> ~/.bashrc
	
# Set environment variables for Conda and Java
ENV PATH="/opt/miniconda/bin:$PATH"
ENV JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"

# Create and activate Python 3.8 environment, install packages
RUN /opt/miniconda/bin/conda create -n py38 python=3.8 -y && \
	echo "conda activate py38" >> ~/.bashrc && \
	/opt/miniconda/bin/conda install -n py38 numpy pandas matplotlib scipy scikit-learn -y

# Set the working directory in the container
WORKDIR /app

# Start bash automatically
CMD ["bash"]	