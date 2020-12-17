# javaLearn
斗地主
package com.还款日期;

import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Calendar;
import java.util.Date;
import java.util.List;

public class EcoBro {
public static void main(String[] args) {
	
	List brData =new ArrayList<>();
	
	//借款日期
	Date  br = new Date();//默认为今天的日期
	//借款期限
	int brMoth =12;
	
	
	SimpleDateFormat sdf=new SimpleDateFormat("yyyy-MM-dd");
	 
	String str=sdf.format(br);
	
	String []strs =str.split("-");
	
	 int  y=Integer.parseInt(strs[0]);//2020
	 int  m=Integer.parseInt(strs[1]);//12
	 int  d=Integer.parseInt(strs[2]);//17
	 
	 
	 for ( int i=0;i<brMoth;i++){
		 Calendar cal =Calendar.getInstance();
		 cal.set(y, m-i, 1);//设置 年月日
		
		 cal.add(Calendar.DAY_OF_MONTH, -1);
		
		 int yy=cal.get(Calendar.YEAR);
		 int mm=cal.get(Calendar.MONTH)+1;
		 int dd=cal.get(Calendar.DAY_OF_MONTH);//每月最大天数
		  
		 int reTurn =d;
		 
		 if(d>dd){
			 reTurn=dd;
		 }
		 String huanKuanDate= yy+"-"+mm+"-"+dd;
		brData.add(huanKuanDate); 
		
	 }
	 System.out.println(brData);//每个月的还款日
}
}
