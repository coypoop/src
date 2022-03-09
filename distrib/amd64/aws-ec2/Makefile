# $NetBSD$

.include <bsd.own.mk>

LIVE_IMAGE=${LIVEIMG_RELEASEDIR}/NetBSD-${DISTRIBVER}-amd64-live.img.gz

.if !exists(${LIVE_IMAGE})
.error "No live image exists, run build.sh live-image first"
.endif

upload_image:
	echo ${LIVEIMG_RELEASEDIR}/NetBSD-${DISTRIBVER}-amd64-live
	#${TOOL_EC2_IMAGEUPLOAD} --sriov --ena \
	NetBSD-9.99.72-amd64-live.img \
	"NetBSD 9.99.72 x86 2020-09-10" \
	"NetBSD/amd64 -current (9.99.72) built on Sep 10 2020" \
	${AWS_REGION} ${S3BUCKET} keyfile.txt
