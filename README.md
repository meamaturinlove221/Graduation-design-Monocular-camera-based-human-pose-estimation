Based on VideoPose3D.
First, use the detectron2 module to detect 2D keypoints in each frame, which contain the position and confidence of each body part.
Then, use an affinity matrix to measure the similarity between different keypoints, and cluster the keypoints that belong to the same body part according to a similarity threshold, and connect them with lines to form the skeleton of the body.
Next, feed the obtained 2D keypoint sequence into a pre-trained 3D pose estimation model, which uses a spatio-temporal convolutional network to capture the dynamic information in the video, and outputs the 3D keypoint coordinates for each frame.
Finally, project the predicted 3D keypoint coordinates onto the 2D plane, and compare them with the original 2D keypoints, calculate the error between them, and update the model parameters according to the error backpropagation, to make the prediction more accurate.
