# Use the latest OSRM backend image
FROM osrm/osrm-backend:latest

# Set the working directory
WORKDIR /data

# Copy the OSM PBF file into the image
COPY ./bangladesh-latest.osm.pbf /data/bangladesh-latest.osm.pbf

# Extract, partition, customize, and run the OSRM server
RUN osrm-extract -p /opt/foot.lua /data/bangladesh-latest.osm.pbf && \
    osrm-partition /data/bangladesh-latest.osrm && \
    osrm-customize /data/bangladesh-latest.osrm

# Specify the command to run the OSRM server
CMD ["osrm-routed", "--algorithm", "mld", "/data/bangladesh-latest.osrm"]
