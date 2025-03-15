# Automated Image Processing System using AWS Lambda  

## Project Overview  
This project is an **Automated Image Processing System** implemented using **AWS Lambda** and **Amazon S3**. It allows users to upload images via **API Gateway** or **S3 event triggers**, processes them by resizing and adding a watermark, and stores the final image in a **processed S3 bucket**.  

## Key Features  
- **Image Upload via API Gateway**: Users can upload images directly via API requests.  
- **S3 Event Triggered Processing**: Automatically processes images when uploaded to an S3 bucket.  
- **Image Resizing**: Converts the image to **300x300 pixels** for optimization.  
- **Watermarking**: Adds a **copyright watermark** to prevent unauthorized use.  
- **Automated Storage**: Saves processed images in a separate **S3 bucket**.  
- **Serverless Deployment**: Uses **AWS Lambda**, reducing infrastructure overhead.  

## Workflow  
1. **Image Upload via API Gateway**:  
   - User sends an image to an **API Gateway endpoint**.  
   - AWS Lambda receives the **base64-encoded image**, decodes it, and uploads it to the **source S3 bucket**.  

2. **Image Upload via S3 Event Trigger**:  
   - If an image is uploaded directly to the **source S3 bucket**, it triggers the **Lambda function**.  

3. **Image Processing (Lambda Function)**:  
   - The function **downloads** the image from the **source S3 bucket**.  
   - **Resizes** the image to **300x300 pixels**.  
   - Adds a **watermark** with the text **"© MyWatermark"**.  
   - Saves the **processed image** in memory.  

4. **Upload to Processed S3 Bucket**:  
   - The final watermarked image is uploaded to the **processed S3 bucket**.  
   - The function returns a success response.  

## AWS Services Used  
- **AWS Lambda**: Runs the image processing script.  
- **Amazon S3**: Stores original and processed images.  
- **Amazon API Gateway** *(Optional)*: Allows users to upload images via API requests.  

## Use Cases  
- **Automated Image Optimization**: Resizes images before storage to reduce size and improve performance.  
- **Watermarking for Copyright Protection**: Protects images from unauthorized use.  
- **E-commerce & Content Management**: Ensures product images are properly formatted before display.  
- **Social Media Automation**: Processes and prepares user-uploaded images for posting.  

## Future Enhancements  
- **Customizable Watermarks**: Allow users to upload custom watermark text or logos.  
- **Advanced Image Editing**: Add filters, cropping, and more transformations.  
- **Multi-Format Support**: Enable support for **PNG, GIF, and WebP** formats.  
- **Image Metadata Processing**: Extract and store metadata for further analysis.  
