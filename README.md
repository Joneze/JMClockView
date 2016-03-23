# JMClockView
利用layer层通过几行代码实现的简易时钟效果

效果如图
 ![image](https://github.com/Joneze/JMClockView/blob/master/JMClockView/111.gif)
 
 关键代码
 
      //convert time to hours, minutes and seconds
      NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSGregorianCalendar];
      NSUInteger units = NSHourCalendarUnit | NSMinuteCalendarUnit | NSSecondCalendarUnit;
      NSDateComponents *components = [calendar components:units fromDate:[NSDate date]];
      CGFloat hoursAngle = (components.hour / 12.0) * M_PI * 2.0;
      //calculate hour hand angle //calculate minute hand angle
      CGFloat minsAngle = (components.minute / 60.0) * M_PI * 2.0;
      //calculate second hand angle
      CGFloat secsAngle = (components.second / 60.0) * M_PI * 2.0;
      //rotate hands
      self.hourHand.transform = CGAffineTransformMakeRotation(hoursAngle);
      self.minuteHand.transform = CGAffineTransformMakeRotation(minsAngle);
      self.secondHand.transform = CGAffineTransformMakeRotation(secsAngle);
