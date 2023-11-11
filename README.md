# Nginx Images Caching

## Run the nginx server

```bash
docker-compose up -d
```

## Wisit this link to receive the image:

[http://localhost:8077/frog.png](http://localhost:8077/frog.png)

### First Request: 

- Response: ![First request response.](./example_images/photo_1.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_miss.jpg)

### Second Request: 

- Response: ![First request response.](./example_images/photo_1.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_miss.jpg)

### Third Request(cache is working): 

- Response: ![First request response.](./example_images/photo_1.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_hit.jpg)

### Replacing the images: 

- With sh: 
```bash
    sh replace_images.sh
```

- With bash:

```bash
    bash replace_images.sh
```

### Fourth request(image not changed):

- Response: ![First request response.](./example_images/photo_1.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_hit.jpg)

### Fifth request(rewriting cache with custom header `frog`):

- Response: ![First request response.](./example_images/photo_2.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_bypass.jpg)

### Sixth request(different photo in cache):

- Response: ![First request response.](./example_images/photo_2.jpg)

- Headers: ![First request headers.](./example_images/photo_cache_hit.jpg)