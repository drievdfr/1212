import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;

public class ResizeImage {
  public static void main(String[] args) {
    try {
      // 读取图片
      BufferedImage originalImage = ImageIO.read(new File("original.png"));

      // 计算新图片的宽度和高度
      int newWidth = 200;
      int newHeight = 200;

      // 创建新图片
      BufferedImage resizedImage = new BufferedImage(newWidth, newHeight, originalImage.getType());

      // 缩放图片
      resizedImage.getGraphics().drawImage(originalImage, 0, 0, newWidth, newHeight, null);

      // 保存新图片
      ImageIO.write(resizedImage, "png", new File("resized.png"));
    } catch (Exception e) {
      e.printStackTrace();
    }
  }
}
