# Data-Analysis-for-LoRaWAN-signal

In this project, we are going to consider the environmental conditions that are integrated with LoRaWAN signal analysis. Considering the public dataset available as "Vineyard 2021" which is an analysis done for 85 days with multiple LoRaWAN nodes placed across 12 sqkm. It records RSSI(Received Signal Strength Indicator), signal-to-noise ratio (SNR), and global positioning system (GPS) information, along with temperature, humidity and pressure data. The motivation of our project is to analyse any statistical pattern that can be drawn out which can further be implemented for industrial as well as academic research task(AI tasks).

# DATASET:
1. SENSOR DATASET:
The sensor dataset describes the radio channel information collected by the LORAWAN gateway. The size of the recording is 190503 records over 3 months.

The rows have values like id, nodeid, timestamp, battery, frequency, data_rate, coding_rate, gtw_id, gtw_channel, gtw_rssi, gtw_snr, soil_temp, soil_hum.

id: for row identification.
node-id: transmitted sensor node identifier.
timestamp: Unix timestamp of the transmission, expressed in the number of seconds.
battery: battery percentage.
frequency: transmitting frequency in MHz.
data_rate: LoRa transmitting bandwidth (BW) in KHz and spreading factor (SF).
coding_rate: the rate of coding for LORA.
gtw_id: the unique identifier of the receiving gateway.
gtw_channel: channel used by the gateway.
gtw_rssi: RSSI measured by the gateway in dBm.
gtw_snr: SNR measured by the gateway in dB.
soil_temp: soil temperature measured by the node in °C.
soil_hum: soil moisture measured by the node in %.
So our first step will be to declare the path of the dataset in the drive and load it in response to a data frame which can done by the pd.read_csv().

2. WEATHER DATASET:
The Weather dataset describes the environmental values collected by the weather station and collected on the endpoint computer using a custom protocol.

The rows have values of timestamp, temperature, humidity, pressure in the atmosphere and precipitation.

Timestamp: Unix timestamp of the acquisition, expressed in number of seconds since January 1, 1970, midnight GMT.
Temp: outdoor temperature in °C.
Hum: outdoor relative humidity in %.
Bar: barometric pressure in hPa.
Rain: rain in mm.
So our first step will be to declare the path of the dataset in the drive and load it in response to a data frame which can done by the pd.read_csv().

3. COMBINED DATASET:
The combined dataset is a combination of the timestamp, temperature, humidity, pressure, rain, RSSI(Received Signal Strength Indicator) signals and the SNR(Signal to Noise Ratio). There are 2029 rows and 21 columns of data.

For RSSI and SNR, we have different nodes together 8 of them.

Timestamp: Unix timestamp of the acquisition, expressed in number of seconds since January 1, 1970, midnight GMT.
Temp: outdoor temperature in °C.
Hum: outdoor relative humidity in %.
Bar: barometric pressure in hPa.
Rain: rain in mm.
RSSI nodes(1-8): It tells how well a device can listen to the signal from the access point.
SNR(1-8): measures the level of a desired signal to the level of background noise.
So our first step will be to declare the path of the dataset in the drive and load it in response to a data frame which can done by the pd.read_csv().

# CONCLUSION:
For this project, we have consider all the dataset that are provided on the one source platform. However, the major analysis is performed over the combined dataset. The conclusion we can draw out is this analytic project provides valuable insights into the interplay between environmental conditions and LoRaWAN signal metrics. While some correlations are evident, careful consideration is required, especially in cases where data limitations result in NaN values. These findings contribute to the understanding of environmental influences on signal strength in LoRaWAN networks, offering avenues for further research and potential applications in both academic and industrial domains. The potential future work that can be implemented using the AI and ML field in terms of predicting models for crop fields, an anomaly in vineyards, climate impact assessment, and one can also using GPS coordinates can analyse the status of each device allocated in different region.

# BIBLIOGRAPHY:
1. The link to the dataset: https://github.com/emanueleg/lora-rssi/tree/master/vineyard-2021_data
2. The link to the supporting paper: Correlation between weather and signal strength in LoRaWAN networks: An extensive dataset; https://www.sciencedirect.com/science/article/pii/S138912862100517X?via%3Dihub
3. Heatmap link: https://bytescout.com/blog/plotting-geographical-heatmaps-using-python-folium-library.html
4. Numpy: https://numpy.org/
5. Pandas: https://pandas.pydata.org/
6. For plots: https://matplotlib.org/

This project is considered under the guidance of Prof. EMANUELE GOLDONI at Università degli Studi di Pavia.
