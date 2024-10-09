# Use the latest OSRM backend image
FROM osrm/osrm-backend:latest

# Set the working directory
WORKDIR /data

# Copy the OSM PBF file into the image
COPY ./bangladesh-latest.osm.pbf bangladesh-latest.osm.pbf

# Extract, partition, customize, and run the OSRM server
RUN osrm-extract -p /opt/car.lua bangladesh-latest.osm.pbf && \
    osrm-partition bangladesh-latest.osrm && \
    osrm-customize bangladesh-latest.osrm  

RUN mkdir /mounted-data    

# Use shell commands to copy files within the container
RUN cp -R /data/* /mounted-data/

# Specify the command to run the OSRM server
# CMD ["osrm-routed", "--algorithm", "mld", "bangladesh-latest.osrm"]
CMD cp -R /data/* /mounted-data/ && osrm-routed --algorithm mld bangladesh-latest.osrm
