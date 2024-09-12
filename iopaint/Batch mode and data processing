pip install tqdm
import os
from tqdm import tqdm  # To display the progress bar in the console
import time  # Used to simulate processing time for demonstration purposes

class IOPaint:
    def __init__(self, model):
        self.model = model
        self.images = []

    def select_batch_mode(self, image_folder):
        """
        Select multiple images from a specified folder for batch processing.
        """
        self.images = [os.path.join(image_folder, f) for f in os.listdir(image_folder) if f.endswith(('jpg', 'png', 'jpeg'))]
        print(f"Selected {len(self.images)} images for batch processing.")

    def process_images(self):
        """
        Process each image in batch mode and save the output.
        Display the progress of processing using a progress bar.
        """
        if not self.images:
            print("No images selected for processing.")
            return

        total_images = len(self.images)
        processed_images = 0
        
        for image_path in tqdm(self.images, desc="Processing Images", unit="image"):
            # Simulate processing
            time.sleep(0.5)  # Replace with actual model processing
            output_image_path = self.model.process(image_path)  # Model's inpainting or outpainting processing
            self.save_output_image(output_image_path)
            
            processed_images += 1
            self.display_progress(processed_images, total_images)
        
        print("Batch processing completed.")

    def save_output_image(self, output_image_path):
        """
        Save the output image after processing.
        """
        # Save logic here, replace with actual save code
        print(f"Output image saved at {output_image_path}")

    def display_progress(self, processed, total):
        """
        Display the progress of the data processing phase and the output picture.
        """
        progress_percentage = (processed / total) * 100
        print(f"Progress: {processed}/{total} images processed ({progress_percentage:.2f}%)")
