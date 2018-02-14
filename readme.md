# S3-Image-Resize

A simple tool that allows you to do inplace image resizing for S3 files.

## Usage
```
const s3Resizer = require('s3-image-resizer');
s3Resizer(<WIDTH>, <HEIGHT>, <S3URL>, <BUCKET>, <KEY>, <ACL>, <ACCESS-KEY>, <SECRET-KEY>);
```

Example code resizing foo.jpg to 800x600 in a directory called images that resides in a bucket called assets and makes it publicly available for reading. Then prints done.
```
const s3Resizer = require('s3-image-resizer');
s3Resizer(
  800,
  600,
  'https://s3-eu-west-1.amazonaws.com/assets/images/foo.jpg',
  'images',
  'assets/foo.jpg',
  'public-read',
  'My-access-key-id',
  'My-secret-key'
)
.then(() => {
  console.log('done');
});
```

## Dependencies
[Sharp](https://www.npmjs.com/package/sharp) for resizing, [Request](https://www.npmjs.com/package/request) for image downloading and [AWS-SDK](https://www.npmjs.com/package/aws-sdk) for AWS interactions.

## License
[MIT](https://opensource.org/licenses/MIT)