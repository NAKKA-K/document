# Shell�̏�����

## shell�����s
	$ bash file.sh
	����
	$ chmod 755 file.sh
	$ ./file.sh
	chmod�̑�1������755�̕����͂�������̎�ނ̃��[�h�����݂���B
	���s�t�@�C���Ƃ��Ă̌����ł����755���g���邱�Ƃ������B
	�ʏ�t�@�C���ł����644�������B


## �ϐ�
date="`date +%H`" #date�ϐ���``�ň͂񂾃R�}���h�̖߂�e�L�X�g�������Ă���B""�ň͂ނ��Ƃɂ���Ĉ��S������{���Ă���B
if [ "$date" == 12 ]; then #""�ň͂ނ��Ƃɂ���āA�ϐ��̒��g�������Ă��G���[�ɂȂ�Ȃ�
  echo "${date}"
fi


## if
if [ A == A ] && [ B == B ]; then #2��̃R�[���Ŏ��s�����
  echo 'true'
elif [ A == A -a B == B ]; then #�I�v�V�����Ƃ��Ă�AND�Ȃ̂ŁA�R�[�������
  echo 'true'
else
  echo 'false'
fi

