# CountDownTimerView
This custom view is used to show count down of time.

![Screenshot 1]
(https://github.com/krishnakapil/CountDownTimerView/blob/master/screenshot.png)

#Usage

Define in xml.<br /><br />
prefixText - Text you want add before the count down timer.<br />
suffixText - Text you want add after the count down timer.<br />
timeMilliSeconds - Time where to start count down from in milliseconds.<br />

```xml
<com.tskk.countdowntimer.ui.CountDownTimerView
  android:layout_width="match_parent"
  android:layout_height="wrap_content"
  app:prefixText="Timer Ends In"
  app:suffixText="!!"
  app:timeMilliSeconds="11430000"
  android:textAppearance="?android:attr/textAppearanceLarge" />
```

Set the time from Java Code
```xml
<com.tskk.countdowntimer.ui.CountDownTimerView
  android:id="@+id/short_timer_view"
  android:layout_width="match_parent"
  android:layout_height="wrap_content"
  android:layout_marginTop="@dimen/activity_vertical_margin"
  android:textAppearance="?android:attr/textAppearanceLarge" />
```

```java
final CountDownTimerView timerView = (CountDownTimerView) findViewById(R.id.short_timer_view);
timerView.setTime(50000);
timerView.setPrefixText("Timer Ends In");
timerView.setSuffixText("!!");
timerView.setOnTimerListener(new CountDownTimerView.TimerListener() {
    @Override
    public void onTick(long millisUntilFinished) {

    }

    @Override
    public void onFinish() {
      timerView.setText("Time up!");
    }
});
```
