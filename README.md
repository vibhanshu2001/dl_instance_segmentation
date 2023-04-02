# dl_instance_segmentation
RCNN model file-> https://github.com/matterport/Mask_RCNN/releases/download/v2.0/mask_rcnn_coco.h5
<br>
If you wish to use the recorded video instead of live camera feed, then just replace the argument from 0 to path of video.
'''
cap = cv2.VideoCapture('path to video file.mp4')
while cap.isOpened():
    ret, frame = cap.read()
    res = segmentation_model.segmentFrame(frame,show_bboxes=True)
    image = res[1]
    cv2.imshow('Instance Segmentation', frame)
    if cv2.waitKey(10) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
'''
