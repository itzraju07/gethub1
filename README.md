package webelement_interface_method;

import java.io.File;
import java.io.IOException;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.io.FileHandler;

public class Task_screenshot_methods {
    
	public static void main(String[] args) throws InterruptedException,IOException {
		System.setProperty("webdriver.chrome.driver", "./drivers/chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.get("https://www.flipkart.com/");
		Thread.sleep(1500);
		
		WebElement head = driver.findElement(By.xpath("//header[@class='_3EOQ5Q']"));
		
		File src= head.getScreenshotAs(OutputType.FILE);
		
		File dest= new File("./screenshots/head.png");
		
		FileHandler.copy(src, dest);
		
		WebElement center = driver.findElement(By.xpath("//div[@class='_3sdu8W emupdz']"));
			
		File src01= center.getScreenshotAs(OutputType.FILE);
			
		File dest01= new File("./screenshots/center.png");
			
		FileHandler.copy(src01, dest01);
		
		
		driver.findElement(By.name("q")).sendKeys("fridge 2 door",Keys.ENTER);
		
        WebElement body = driver.findElement(By.xpath("//a[@class='k7wcnx']"));
		
		File src1= body.getScreenshotAs(OutputType.FILE);
		
		File dest1= new File("./screenshots/body.png");
		
		FileHandler.copy(src1, dest1);
		
		driver.quit();
		
		
	}
}
