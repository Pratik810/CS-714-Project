Hello My Name is Pratikkumar patel 
Student id 200486081

i would like to share my code and other documentation with you. i have upload all the necessary documentation in that folder
Here is link: https://drive.google.com/drive/folders/1YmHDe1YBBv4PjvrFVIZ2LRNZvPi8IlBJ?usp=sharing

How to run the code?

i have used google colab environment. to upload and run the .ipynb file

1.Upload the Image_to_image_translation_GAN.ipynb file in google colab runtime.

2.Upload the Pretrained model that i have already download after running the code for 10 epochs.
  Just upload model_010960.h5 file in colab runtime. You can find this file in  google drive link 
  

3. Upload the Dataset in this filename maps.tar or else you can use  images from this folder
   maps/train. you can find dataset from the above drive link.

4. You don't need to run the whole code just upload pre-trained model (model_010960.h5) and run 
   from keras.models import load_model
   from numpy.random import randint
   model = load_model('model_010960.h5') 
   this cell in this Image_to_image_translation_GAN.ipynb file. 

   then run this cell in this Image_to_image_translation_GAN.ipynb file
   # plot source, generated and target images
   def GENERATE_IMAGES_USING_MODEL(src_img, gen_img, tar_img):
	images = vstack((src_img, gen_img, tar_img))
	# scale from [-1,1] to [0,1]
	images = (images + 1) / 2.0
	titles = ['Source', 'Generated', 'Expected']
	# plot images row by row
	for i in range(len(images)):
		# define subplot
		pyplot.subplot(1, 3, 1 + i)
		# turn off axis
		pyplot.axis('off')
		# plot raw pixel data
		pyplot.imshow(images[i])
		# show title
		pyplot.title(titles[i])
	pyplot.show()
    [X1, X2] = dataset
    # select random example
    num_samples = 5

    for _ in range(num_samples):
    ix = randint(0, len(X1), 1)
    src_image, tar_image = X1[ix], X2[ix]
   # generate image from source
   gen_image = model.predict(src_image)
   # plot all three images
  GENERATE_IMAGES_USING_MODEL(src_image, gen_image, tar_image)


and you will get 5 random sample images of 
   Aerial <-> Map images.