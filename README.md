# ANDROID calculator - chat GPT AI conversation (prompt + reply)

Richard Renyi-Vamos
create a calculator app in android
To create a calculator app in Android, follow these steps:

Step 1: Create a new Android Studio project

Open Android Studio and create a new project.
Choose "Empty Activity" as the project template.
Give your project a name and set the package name as per your choice.
Step 2: Design the UI

Open the "activity_main.xml" file in the "res/layout" directory.
Design the UI for your calculator app by adding buttons for digits, operators, and the result.
You can use the Grid Layout to arrange the buttons in a calculator-like layout.
Step 3: Add button click events

Open the MainActivity.java file.
Add button click events for the digits, operators, and the result button.
In the button click events, you can perform the necessary calculations based on the user input and display the result in a TextView.
Here's an example of the code you can use:

MainActivity.java

java
Copy code
public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    private TextView resultTextView;
    private String operand1 = "";
    private String operand2 = "";
    private String operator = "";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        resultTextView = findViewById(R.id.resultTextView);

        findViewById(R.id.btn0).setOnClickListener(this);
        findViewById(R.id.btn1).setOnClickListener(this);
        findViewById(R.id.btn2).setOnClickListener(this);
        findViewById(R.id.btn3).setOnClickListener(this);
        findViewById(R.id.btn4).setOnClickListener(this);
        findViewById(R.id.btn5).setOnClickListener(this);
        findViewById(R.id.btn6).setOnClickListener(this);
        findViewById(R.id.btn7).setOnClickListener(this);
        findViewById(R.id.btn8).setOnClickListener(this);
        findViewById(R.id.btn9).setOnClickListener(this);
        findViewById(R.id.btnAdd).setOnClickListener(this);
        findViewById(R.id.btnSubtract).setOnClickListener(this);
        findViewById(R.id.btnMultiply).setOnClickListener(this);
        findViewById(R.id.btnDivide).setOnClickListener(this);
        findViewById(R.id.btnResult).setOnClickListener(this);
    }

    @Override
    public void onClick(View v) {
        switch (v.getId()) {
            case R.id.btn0:
                numberPressed("0");
                break;
            case R.id.btn1:
                numberPressed("1");
                break;
            case R.id.btn2:
                numberPressed("2");
                break;
            case R.id.btn3:
                numberPressed("3");
                break;
            case R.id.btn4:
                numberPressed("4");
                break;
            case R.id.btn5:
                numberPressed("5");
                break;
            case R.id.btn6:
                numberPressed("6");
                break;
            case R.id.btn7:
                numberPressed("7");
                break;
            case R.id.btn8:
                numberPressed("8");
                break;
            case R.id.btn9:
                numberPressed("9");
                break;
            case R.id.btnAdd:
                operatorPressed("+");
                break;
            case R.id.btnSubtract:
                operatorPressed("-");
                break;
            case R.id.btnMultiply:
                operatorPressed("*");
                break;
            case R.id.btnDivide:
                operatorPressed("/");
                break;
            case R.id.btnResult:
                calculateResult();
                break;
        }
    }

    private void numberPressed(String number) {
        if (operator.isEmpty()) {
            operand1 += number;
            resultTextView.setText(operand1);
        } else {
            operand2 += number;
            resultTextView.setText(operand2);
        }
    }

    private void operatorPressed(String op) {
        if (operator.isEmpty()) {
            operator = op;
        } else {
            calculateResult();
            operator = op;
        }
    }

    private
