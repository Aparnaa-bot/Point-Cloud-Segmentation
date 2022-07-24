# Point-Cloud-Segmentation
DL_PointNet

In Artificial Intelligence, Computer Vision plays a major part in Deep Learning Techniques.
Image Recognition , Object Detection, Object Classification or Segmentation is used everyday
in various fields such as Autonomous Systems, Robotics, Health Care Motion Recognition and
Monitoring to detect and analyze images or videos and produce the desired result and played
a key role in Artificial Intelligence real world applications to bring it to reality. 
Such various Object Detection techniques in real time are operated with 2D images. In recent times, the
trend of 3d images has risen where it is an unstructured data and can be used to provide more
accuracy of shape , location or structure and provide in depth analysis, information retrieval of
the image. Point clouds are 3D digital images with a series of points with three coordinates that
represent the position of the object. Hence this paper proposes the work of segmenting object
parts of 3D point clouds using normalized point clouds data and implementing it PointNet deep
learning architecture and also providing various applications of point clouds segmentation and
comparing it with pointnet++ deep learning model.

Working of PointNet
.
Max Pooling
Max pooling is a simple operation that computes the maximum value of the input of a feature
used for down-sampling the feature of the original input and also retains the maximum information possible. This is necessary to avoid over fitting of the data by extracting the utmost
information possible as well as reduces the computational cost of the network by reducing the
number of parameters to learn/train, in 2D it works by simply reducing the number of pixels
of the image. There are different types of pooling layers available for building the block in
CNN such as maximum pooling , Average pooling, minimum pooling. Average and maximumpooling are the two types of commonly used pooling layers in CNN. Coming to the PointNet
architecture it is said that Maximum pooling [ ] works best in point clouds. In pointNet Max
Pooling works as a symmetry function. There are many symmetry functions that can be used
but here it uses only a simple symmetry function to sum the information from each point from
the input. It take n vector as input and a new vector is produced which is constant to input. This
is necessary because the point set are not ordered and due to high dimension of the data sorting
can no resolve the issue.

Gathering Local and Global features
The output from the pointnet vanilla forms a vector. For the purpose of classification, the model
can easily train MLP on global features obtained for classification,but this cant be done for
segmentation. First the global point cloud feature is computed then it is sent back to each points
by adding the global features with local each points again, then from this a new point features
is extracted in previous round where these new points are aware about the global features and
and local point features. Hence with this network where it concatenates both local and global
information’s to the points it has knowledge about the outline and inner-line about the feature ,
hence the semantic segmentation is done.

2 Joint Alignment Network
As mentioned earlier the point clouds must be invariant to any geometry transformation in order
to make semantic labelings. Hence a T-net transformation is applied directly to the inputs . This
transformation matrix has higher dimension. In the final step of transformation the input points
which are fully dependent is combined with biases and weights in 3X3 transformation matrix.
This is to completely ensure that the point sets are invariant to any kind of transformation like
rotation, translation etc.
