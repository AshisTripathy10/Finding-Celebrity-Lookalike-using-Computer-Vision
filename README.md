Introduction: With this project, we discover a fun way to find our celebrity look-alike. To achieve this, we use the face_recognition library, which is built on top of dlib’s state-of-the-art face recognition developed with deep learning. Dlib is a powerful C++ toolkit, but it also has Python bindings, allowing us to leverage its advanced machine learning algorithms and facial recognition tools directly in a Jupyter Notebook.

Creating the Directory Structure: We create the directory structure using !mkdir, where we upload our photographs. The ! is necessary because Jupyter Notebook cells are primarily for Python code, but the ! prefix lets us execute shell commands without leaving the notebook environment. 

Importing the Libraries: We import face_recognition, os, numpy and IPython.display’s Image libraries for our project. 

Function to Load Images and Face Encodings: We define a function load_images() that takes a directory path as its argument. It loads each image using load_image_file() and generates a 128-dimensional face encoding using face_recognition.face_encodings(), with FaceNet (introduced by Google in 2015) capturing key facial features. Valid encodings and filenames are stored in lists and returned as a tuple.

Calculating Euclidean Distance: The function calculate_face_distance() takes a list of known face encodings and the file path of an unknown image. It encodes the unknown image and computes the Euclidean distance between its encoding and the known encodings using face_recognition.face_distance(). The function finds the closest match by identifying the minimum distance and returns a tuple with the unknown image path and the filename of the closest known image.

Loading the Images: We use the load_images() function to load celebrity images by providing the directory path. The file path of our image is stored in original_image, which is then displayed.

Finding the Matching Celebrity Image: The calculate_face_distance function is called with known_encodings (from celebrity images) and original_image (our image’s file path). It compares the face in original_image to those in known_encodings and returns the path to the most similar image. The [1] extracts the filename of this closest match, which is then plotted alongside our image using Matplotlib.
