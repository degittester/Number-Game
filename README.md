# About the game
***
 An individual will have to guess the number between 0 to 100 within 5 attempts, if not then he/she will lose.
 Hints will also be provided after your attempt is wrong. (If your guess is smaller than the answer then it will display that your answer is smaller and vice versa)
***
#### How it is build?
This app is built-in Android Studio using JAVA language. 
* Select the Android Studio blank activity which also adds content.xml in which you design your layout.
* Then, add text view(for displaying hints), edit view(for taking the response), buttons(overriding onClickListener button to respond according to your response)
in an XML file with an ID assigned to each component.
* Now, create a second activity as a Default type to show the result into it(i.e Won/Loose) and add a text view in the XML file of the second activity.
* Write down the following java code inside the onCreate function
***
	   submitBtn = (Button) findViewById(R.id.submitBtn);
        submitBtn.setOnClickListener(new View.OnClickListener() {
            public void onClick(View view) {
                try {
                     numCheck = Integer.parseInt(firstEditText.getText().toString());
                }
                catch(Exception e) {
                }

                if (num == numCheck || chance == iterate) {
                    if (chance == iterate) {
                        str = "***You lost***";
                        submitBtn.setEnabled(false);
                    } else
                        str = "***Bingo***";
                    Intent i = new Intent("com.example.SecondActivity");
                    i.putExtra("key1", str);
                    startActivity(i);
                }


                if (numCheck <= 100 && numCheck >= 0) {
                    iterate++;
                    if (num < numCheck) {
                        tv4.setText("Guess is larger.");
                    }
                    if (num > numCheck) {
                        tv4.setText("Guess is smaller.");
                    }
                } else {
                    tv4.setText("Invalid Option");
                }
            }
        });
***
* *THAT'S IT* Good start to kick off your career as Android Developer.
