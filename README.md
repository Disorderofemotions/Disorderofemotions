public class Main extends Activity implements @Override
  public void onAccuracyChanged(Sensor sensor, int accuracy) { //Изменение точности показаний датчика
  }

@Override
  protected void onResume() {
  }

@Override
  protected void onPause() {
  }

@Override
  public void onSensorChanged(SensorEvent event) { //Изменение показаний датчиков
  }

    private SensorManager mSensorManager; 
  private Sensor mOrientation;

  private float xy_angle;
  private float xz_angle;
  private float zy_angle;

  private TextView xyView;
  private TextView xzView;
  private TextView zyView;

  public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.main);

    mSensorManager = (SensorManager) getSystemService(Context.SENSOR_SERVICE); // Получаем менеджер сенсоров
    mOrientation = mSensorManager.getDefaultSensor(Sensor.TYPE_ORIENTATION); // Получаем датчик положения
    
    xyView = (TextView) findViewById(R.id.xyValue);  //
    xzView = (TextView) findViewById(R.id.xzValue);  // Наши текстовые поля для вывода показаний
    zyView = (TextView) findViewById(R.id.zyValue);  //
  }
public void onSensorChanged(SensorEvent event) {
    xy_angle = event.values[0]; //Плоскость XY
    xz_angle = event.values[1]; //Плоскость XZ
    zy_angle = event.values[2]; //Плоскость ZY
    
    xyView.setText(String.valueOf(xy_angle));
    xzView.setText(String.valueOf(xz_angle));
    zyView.setText(String.valueOf(zy_angle));
}
  
  
