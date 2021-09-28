# Image Processing

The simple image processing program, It takes directory name as command line argument and processes all images in that directory to create the thumbnail images. It uses https://github.com/disintegration/imaging go module internally to do actual image processing.
ex. `go run main.go ../images/`

## Serial
In the serial directory, it process all images serially.

## Pipeline
To improve the performance of image processing program we need to add concurrency. It is intuitive to use pipeline pattern in this case because each image is processed in 3 different stages.

```
walkfile ----------> processImage -----------> saveImage
           (paths)                  (results)

```

