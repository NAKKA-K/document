# Git Reference

## GitHub�ɐV����Push����Ƃ��ɂ悭�g���R�}���h
### git remote add origin https://github.com/.../....git
	URL��origin�Ƃ����j�b�N�l�[����t����Ƃ����Ӗ��ł��B
	��������邱�Ƃɂ���Ĉȍ~��URL����͂����Ƃ��Aorigin�Œu�������邱�Ƃ��ł��܂��B


## �����[�g���|�W�g���Ɏ����̕ύX�𔽉f�������ꍇ
### git push -u origin master
	���[�J���̓��e��orogin�Ƃ��������[�g�T�[�o�ɑ΂��ăA�b�v���[�h���܂��B�w�肷��u�����`��master�B
	master�̕����͏ȗ����ď�����Ă���̂ŁA�ȗ����Ȃ��ꍇmaster:master�Ə����܂��B(���[�J��master���烊���[�gmaster��)


## �����[�g���|�W�g����push����O�ɂ��邱��
### git pull
	pull����ƃ��[�J���ɕύX���Ȃ��ꍇ�Afast-forword-marge�����B���̏ꍇ�A���̂܂�push�ł���B
	���[�J���ɕύX���������ꍇ�A��������B���������Ƃ��̓t�@�C����
	<<<HEAD
	===
	>>>sample
	�̕����𒼂�����Acommit����B


## �����[�g���|�W�g���̓��e�������������ꍇ
### git fetch
	�����[�g���|�W�g���̍ŐV�̗����̎擾�������s�����Ƃ��ł��܂��B
	�擾�����R�~�b�g�͖��O�̂Ȃ��u�����`�Ƃ��Ď�荞�܂�܂��B
	���̃u�����`�ɂ�FETCH_HEAD�Ƃ������O�Ń`�F�b�N�A�E�g���邱�Ƃ��ł��܂��B
	���̏�Ԃ���fetch�������e�����[�J���ɓ�������ꍇ�́AFETCH_HEAD��marge�A����pull�����s���܂��B
	pull�Ƃ͓�����fetch + marge�����Ă��܂��B���̂���marge�Ɠ��������ɂȂ�܂��B


## ���̑��̃R�}���h
### echo �����̏o��
	-n �Ō�̉��s������
	>> �t�@�C���̍Ō�ɒǉ�

### git diff ���dir��stage�̕ύX�_��\��
	--staged �X�e�[�W���O�G���A�ƃR�~�b�g�����̕ύX�_��\��(-s)

### git commit stage����R�~�b�g�����ɒǉ�
	-a ���dir����R�~�b�g�����ɒǉ�

### bash file.sh shell�����s

### git add ���dir����stage�ɒǉ�
	--dry-run �ǉ������t�@�C�����(�\�s���K)(-n)

### git log    �R�~�b�g������\��
	--shortstat �R�~�b�g�ł̕ύX�_��\��
	--pretty=oneline onelie���g�p�����ꍇ�ȗ������ASHA1ID���ڍו\������
	--graph �u�����`�����o�������
	--decorate tag,tip,HEAD�����\�������
	--all �S�Ẵu�����`��\������

