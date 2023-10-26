- 👋 Hi, I’m @Disorderofemotions
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Disorderofemotions/Disorderofemotions is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

/ метод определения точности датчиков
@override
public void onAccuracyChanged (Sensor sensor, int 1) f
@Override
protected void onResume() {
super. onResume (;
sensorManager registerListener (Listener, accelerometerSensor, SensorManager. SENSOR_DELAY_UT);
@Override
protected void onPause {
super…onPause;
sensorManager unregisterListener (Listener);
