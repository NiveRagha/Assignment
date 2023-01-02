package sample.test;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.awt.AWTException;
import java.awt.Button;
import java.awt.Robot;
import java.util.Set;

public class Polytrade {

public static void main(String[] args) throws AWTException, InterruptedException {
// TODO Auto-generated method stub
       System.setProperty("webdrive.chrome.driver", "C:\\chromedriver_win32\\chromedriver.exe");
       WebDriver driver=new ChromeDriver();
       driver.manage().window().maximize();
       driver.get("https://lender.polytrade.app/");
       driver.findElement(By.xpath("//*[text()='Skip']")).click();
       Thread.sleep(7000);
  driver.findElement(By.id("connect")).click();
  Thread.sleep(5000);
  driver.findElement(By.xpath("(//*[text()='Connect'])[3]")).click();
  Thread.sleep(5000);
  if( driver.findElement(By.xpath("//*[@id='walletconnect-qrcode-close']")).isDisplayed())
  driver.findElement(By.xpath("//*[@id='walletconnect-qrcode-close']")).click();
  Thread.sleep(5000);
  //WebElement element = driver.findElement(By.linkText("//*[text()='APR']"));
  //((JavascriptExecutor)driver).executeScript("arguments[0].scrollIntoView(true);", element);
  JavascriptExecutor jsx = (JavascriptExecutor)driver;
  jsx.executeScript("window.scrollBy(0,950)", "");
  Thread.sleep(5000);
 ////*[@id="pool"]/div[1]/div[1]/div[2]/h2
 
  //if(driver.findElement(By.linkText("//*[text()='APR']")).isDisplayed()) System.out.println("APR Page has been loaded");
  if(driver.findElement(By.xpath("//*[@id='pool']/div[1]/div[1]/div[2]/h2")).getText().contains("APR"))
  System.out.println("APR Page has been loaded");
  else
  System.out.println("APR Page not found");
 
 String TotalPolytradeDeposits= driver.findElement(By.xpath("//*[@id='overview']/div[1]/div/h3")).getText();
  String TotalInvoicesFunded= driver.findElement(By.xpath("//*[@id='overview']/div[2]/div/h3")).getText();
 String CurrentPoolLiquidity= driver.findElement(By.xpath("//*[@id='pool']/div[1]/div[4]/div/div[2]/h5")).getText();
 String FixedAPR= driver.findElement(By.xpath("//*[@id='pool']/div[1]/div[5]/div/div[2]/h5")).getText();
 System.out.println("TotalPolytradeDeposits : "+TotalPolytradeDeposits);
 System.out.println("TotalInvoicesFunded : "+TotalInvoicesFunded);
 System.out.println("CurrentPoolLiquidity : "+CurrentPoolLiquidity);
 System.out.println("FixedAPR : "+FixedAPR);
