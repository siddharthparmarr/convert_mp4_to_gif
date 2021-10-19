just in case if i forget it again ...

```
ffmpeg -i in.mp4 -filter:v "crop=900:700:0:50" out.mp4
```
```
crop=w:h:x:y
```
Generate Palette
```
ffmpeg -y -i out.mp4 -vf fps=5,scale=600:-1:flags=lanczos,palettegen palette.png


```


Convert to gif
```
ffmpeg -i out.mp4 -i palette.png -filter_complex "fps=5,scale=600:-1:flags=lanczos[x];[x][1:v]paletteuse" out.gif

```

