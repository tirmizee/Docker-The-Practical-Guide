### Linux “Distro” in Docker

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/114679645-8fb91b80-9d36-11eb-8137-d698ed262333.JPG" width="600">
</p>

### Environment variables ใน Dockerfile

#### FROM

 - ###### เริ่มต้นขั้นตอนการสร้าง  Base Image. Dockerfile ที่ถูกต้องจะต้องเริ่มต้นด้วยคำสั่ง FROM

#### LABEL

#### ENV

#### EXPOSE

- ###### คำสั่ง EXPOSE ไม่ได้เผยแพร่พอร์ตจริง ทำหน้าที่เป็นเอกสารประเภทหนึ่ง

#### ARG

#### WORKDIR

#### ADD

- ###### คำสั่ง COPY เป็นคำสั่งคัดลอกไฟล์หรือไดเรกทอรีใหม่จาก host และเพิ่มลงในระบบไฟล์ของคอนเทนเนอร์ไปยังเส้นทางปลายทางที่ระบุพร้อมกับแตกไฟล์ให้กรณีที่เป็น tar

#### COPY

- ###### คำสั่ง COPY เป็นคำสั่งคัดลอกไฟล์หรือไดเรกทอรีใหม่จาก host และเพิ่มลงในระบบไฟล์ของคอนเทนเนอร์ไปยังเส้นทางปลายทางที่ระบุ

#### RUN

#### CMD

#### ENTRYPOINT

#### VOLUME

#### ONBUILD

#### STOPSIGNAL

#### HEALTHCHECK

#### SHELL





### Reference

- https://docs.docker.com/glossary
