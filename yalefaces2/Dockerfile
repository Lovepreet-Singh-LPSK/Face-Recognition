FROM python:3.6

RUN pip install opencv-python==3.4.10.37
RUN opencv_createsamples -info yalefaces.info -num 166 -w 320 -h 243 -vec yalefaces.vec
