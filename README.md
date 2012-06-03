where_is_my_MARTA_train
=======================

See real-time location of MARTA subway trains in a mobile app to gauge whether or not you need to run to station in order to catch a train!

After cloning this git repository, run this command in the directory:

java -Xms1024M -Xmx1024M -jar rhok_marta.jar "marta gtfs"/ trains.pb 1000

where "marta gtfs/" is the directory containing your GTFS directory, "trains.pb" is the vehicle location data in protocol buffer format & "1000" is the number of milliseconds to output updated vehicle locations

Then, clone https://github.com/OneBusAway/onebusaway-gtfs-realtime-visualizer.git and copy the HTML & CSS contents from this repo's www directory into the "src/main/resources/org/onebusaway/gtfs_realtime/visualizer" subdirectory of the onebusaway-gtfs-realtime-visualizer project you will have just cloned.

And run the visualizer app: java -jar target/onebusaway-gtfs-realtime-visualizer-0.0.1-SNAPSHOT.jar   --vehiclePositionsUrl=file:///<your file directory path>/where_is_my_MARTA_train/trains.pb

Finally, assuming you're located in Atlanta, you can open http://localhost:8080 in your browser and see MARTA train icons move around in a Google Map in real-time! (tested with Google Chrome Canary)