checkBoxListener = new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            if(blueCheckBox.isChecked()){
                //Change theme to blue
            }
            if(redCheckBox.isChecked()){
                //Change theme to red
            }
            if(greenCheckBox.isChecked()){
                //Change theme to green
            }
            if(bwCheckBox.isChecked()){
                 //Change theme to Black & White
            }
        }
    };
    blueCheckBox.setOnClickListener(checkBoxListener);
    redCheckBox.setOnClickListener(checkBoxListener);
    greenCheckBox.setOnClickListener(checkBoxListener);
    bwCheckBox.setOnClickListener(checkBoxListener);
}
