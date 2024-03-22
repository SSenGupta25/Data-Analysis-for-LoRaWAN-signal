# Data-Analysis-for-LoRaWAN-signal

In this project we are going to consider the environmental conditions that are integrated with LoRaWAN signal analysis. Considering the public dataset available as "Vineyard 2021" which is an analysis done for a period of 85 days with multiple LoRaWAN nodes placed across 12 sqkm. It records about RSSI(Received Signal Strength Indicator), signal to noise ratio (SNR), global positioning system (GPS) information, along with temperature, humidity and pressure data. The motivation of our project is to analyse any statical pattern that can be drawn out which can futhur be implemented for industrial as well as academic research task(AI tasks).

# DATASET:
1. SENSOR DATASET:
The sensor dataset describes the radio channel information collected by the LORAWAN gateway. The size of the recording is of 190503 records over a span of 3 months.

The rows have values like id, nodeid, timestamp, battery, frequency, data_rate, coding_rate, gtw_id, gtw_channel, gtw_rssi, gtw_snr, soil_temp, soil_hum.

id: for row identification.
nodeid: transmitted sensor node indentifier.
timestamp: Unix timestamp of the transmission, expressed in number of seconds.
battery: battery percentage.
frequency: transmitting frequency in MHz.
data_rate: LoRa transmitting bandwidth (BW) in KHz and spreading factory (SF).
coding_rate: the rate of coding for LORA.
gtw_id: unique identifier of the receiving gateway.
gtw_channel: channel used by the gateway.
gtw_rssi: RSSI measured by the gateway in dBm.
gtw_snr: SNR measured by the gateway in dB.
soil_temp: soil temperature measured by the node in °C.
soil_hum: soil moisture measured by the node in %.
So our first step will be to decleare the path of the dataset in the drive and load it in resprestation of a data frame which can done by the pd.read_csv().

2. WEATHER DATASET:
The Weather dataset describe the environmental values collected by the weather station and collected on the end point computer using a custom protocol.

The rows have values of timestamp, temperature, humidity, pressure in the atmosphere and precipitation.

Timestamp: Unix timestamp of the acquisition, expressed in number of seconds since January 1, 1970, midnight GMT.
Temp: outdoor temperature in °C.
Hum: outdoor relative humidity in %.
Bar: barometric pressure in hPa.
Rain: rain in mm.
So our first step will be to decleare the path of the dataset in the drive and load it in resprestation of a data frame which can done by the pd.read_csv().

3. COMBINED DATASET:
The combined dataset is a combination of the timestamp, temperature, humidity, pressure, rain, RSSI(Received Signal Strength Indicator) signals and the SNR(Signal to Noise Ratio). There are 2029 rows and 21 columns of data.

For RSSI and SNR we have different nodes all together 8 of them.

Timestamp: Unix timestamp of the acquisition, expressed in number of seconds since January 1, 1970, midnight GMT.
Temp: outdoor temperature in °C.
Hum: outdoor relative humidity in %.
Bar: barometric pressure in hPa.
Rain: rain in mm.
RSSI nodes(1-8): It tells how well a device can listen to the signal from the access point.
SNR(1-8): measures the level of a desired signal to the level of background noise.
So our first step will be to decleare the path of the dataset in the drive and load it in resprestation of a data frame which can done by the pd.read_csv().

# CONCLUSION:
In conclusion, the analysis reveals subtle relationships between environmental factors and the performance metrics of the LoRaWAN network in the vineyard.
Temperature exhibits a weak positive association with total Signal-to-Noise Ratio (SNR) and moderate negative with total Received Signal Strength Indicator (RSSI).
Atmospheric pressure shows a weak positive correlation with total SNR, and much better positive correlation with RSSI.
While rain has a minimal impact on both total SNR and total RSSI, as indicated by weak positive correlations. However, RSSI is better valued than SNR.
Humidity demonstrates a weak positive relationship with total SNR and a moderate positive association with total RSSI.
Eventhough they are weak but there is a relationship between RSSI and temperature which made it almost linear and also the correlation matrix suggests a linear relationship between RSSI and absolute humidity.
Plots indicate that LoRa RSSI and meteorological parameters are correlated, and with our dataset, more research may be profitably done to determine the links between the two.
