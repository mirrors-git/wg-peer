# Find Files in Time Range

Recursively search for all files whose last modification time is in a specified range.

```
fftr path {time|file} range [b]
```

where:
- **path** is where to start the search
- **time** is any format understood by `date -d`
- **file** is a reference file (`now` is a time, hence use `./now`)
- **range** in seconds; +N after time, -N before time, N centered on time
- (optional) **b** means bare output

### Examples
- find files modified at most 2 day ago: `fftr . now -2*24*60*60`
- find files modified at most 1 second before or after the time of myfile: `fftr . myfile 2`
- find files modified at most 2 hours after the time of a file named 'now': `fftr ./now +2*60*60`
- move files modified at most 7 days ago: `mv $(fftr . now -7*24*60*60 b) /else/where`

### Screenshots
![Screenshot](https://images2.imgbox.com/0c/a5/i8xYgyra_o.png)
![Screenshot](https://images2.imgbox.com/80/1a/ms4yfnvb_o.png)
![Screenshot](https://images2.imgbox.com/47/1f/9m6yLhJI_o.png)