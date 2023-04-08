package AmazonTest;

import java.io.File;
import java.io.IOException;
import java.util.List;
import java.util.concurrent.TimeUnit;

import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class AmazonTest {

	public static void main(String[] args) throws InterruptedException, IOException {
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver", "chromedriver.exe");
		ChromeDriver driver = new ChromeDriver();
		driver.get("https://www.amazon.in/");

		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(3000, TimeUnit.MICROSECONDS);

		WebElement searchBox = driver.findElement(By.id("twotabsearchtextbox"));
		searchBox.sendKeys("Samsung Mobiles");

		WebElement searchBox1 = driver.findElement(By.id("nav-search-submit-button"));
		searchBox1.click();

		List<WebElement> Product = driver.findElements(By.xpath("//div[@class='a-section']//h2//span"));

		List<WebElement> Price = driver
				.findElements(By.xpath("//div[@class='a-section']//a//span[@class='a-price-whole']"));

		List<WebElement> Symbol = driver
				.findElements(By.xpath("//div[@class='sg-row']//span[@class='a-price-symbol']"));

		for (int i = 0; i < Product.size(); i++) {
			System.out.println("Product : " + Product.get(i).getText());
			System.out.println("Price : " + Symbol.get(i).getText() + " " + Price.get(i).getText());
		}

		TakesScreenshot obj = (TakesScreenshot) driver;
		File fileobj = obj.getScreenshotAs(OutputType.FILE);
		File screenshotObj = new File("src/ImageSource/image.png");
		
		FileUtils.copyFile(fileobj, screenshotObj);
		driver.close();

	}
}
