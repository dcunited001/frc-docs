# Working with Contours

After thresholding and removing noise with morphological operations, you are now ready to use OpenCV's ``findContours`` method. This method allows you to generate contours based on your binary image.

## Finding and Filtering Contours

.. tab-set-code::


In cases where there is only one vision target, you can just take the largest contour and assume that is the target you are looking for. When there is more than one vision target, you can use size, shape, fullness, and other properties to filter unwanted contours out.

.. tab-set-code::


If you draw the contour you just found, it should look something like this:

.. image:: images/using-cameraserver/red-outline.jpg
   :alt: Retroreflective tape outlined in red by the image processing algorithm.

## Extracting Information from Contours

Now that you've found the contour(s) that you want, you now want to get information about it, such as the center, corners, and rotation.

### Center

.. tab-set-code::


### Corners

.. tab-set-code::


### Rotation

.. tab-set-code::


For more information on how you can use these values, see :ref:`docs/software/vision-processing/introduction/identifying-and-processing-the-targets:Measurements`

## Publishing to NetworkTables

You can use NetworkTables to send these properties to the Driver Station and the RoboRIO. Additional processing could be done on the Raspberry Pi, or the RoboRIO itself.

.. tab-set-code::


