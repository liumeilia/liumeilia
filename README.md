#include<stdio.h>
#include<stdlib.h>
#include<string.h>

//建立一个教室链表，包含教室的基本信息
typedef struct classroom{
	char address;
	int area;
	int seatnumber;
	char type;
	char ad;
	struct classroom *next;
}classroom; 

//初始化一个单链表
classroom *initclass(classroom *head){
	head = (classroom*)malloc(sizeof(classroom));
	if(head == NULL){//申请空间失败 
		printf("申请空间失败");
		return 0;
	}
	head->next = NULL;
	return head; 
} 

//输入数据
classroom *creatroom(classroom *head,char address1,int area1,int seatnumber1,char type1,char ad1)
{
	classroom *p,*s;
	s = (classroom *)malloc(sizeof(classroom));
	if(s == NULL){
		return 0;
		printf("申请空间失败"); 
	}

	p = head;
	
	s->address = address1;
	s->area = area1;
	s->seatnumber = seatnumber1;
	s->type = type1;
	s->ad = ad1;
	
	p->next = s;
	//printf("hdiruiaw");
	p = s;
	p->next = NULL;

	return p; 
 } 
 
 int main(){
 	classroom *head;
 	char address1;
	int area1;
	int seatnumber1;
	char type1;
	char ad1;
	head = initclass(head);
	int i=0;
	for(i=0;i<3;i++){
		printf("请输入教室的地址、面积、座位数、教室类型、管理员");
		scanf("%s,%d,%d,%s,%s",&address1,&area1,&seatnumber1,&type1,&ad1);
		head = creatroom(head,address1,area1,seatnumber1,type1,ad1);
	}
	classroom *p;
	p = head;
	while(p->next!=NULL){
		printf("%s%d%d%s%s",p->address,p->area,p->seatnumber,p->type,p->ad);
		p=p->next;
	}
 	return 0;
 } 
 
 
