# Architecture

The two main entities in Tubely are `videos` and `users`. A `user` can have many `videos`, and a `video` belongs to a single `user`.


## Users
| Properties    |
| ------------- |
| created_at    |
| email         |
| id            |
| refresh_token |
| token         |
| updated_at    |

[Creating a new user](./ui.md#creating-a-new-user)

## Videos
| Properties    |
| ------------- |
| created_at    |
| description   |
| id            |
| thumbnail_url |
| title         |
| updated_at    |
| user_id       |
| video_url     |

"Videos" have 3 things to worry about:
1. Metadata: The title, description, and other information about the video
2. Thumbnail: An image that represents the video
3. Video: The actual video file

Tubely allows users to create a "new draft" - which creates a new video record in the database containing *metadata only*. Thumbnails and video files are uploaded separately after the draft is created.  
[Creating a video draft](./ui.md#creating-a-video-draft)

Tubely uses the [multipart/form-data](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods/POST#multipart_form_submission) encoding format. This is a way to send multiple pieces of data in a single request and is commonly used for file uploads. It's the "default" way to send files to a server from an HTML form. The `handlerUploadThumbnail` function uses this encoding to store thumbnail data in memory.
