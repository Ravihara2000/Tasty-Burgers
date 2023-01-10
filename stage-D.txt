#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<time.h>
#include<conio.h>

enum Burger_types{Chicken=1,Ham=2,Vegie=3};

struct chips{
	char cdescription[50];
	float min_weight;
};

struct drinks{
	char ddescription[50];
	int quantity;
};

struct burger{
	enum Burger_types Burger_type;
	int  quantity;
};

struct meals{
	struct burger *p1;
	struct chips  *p2;
	struct drinks *p3;
};

struct order{
	int receipt_no;
	float total_price;
	struct burger *add;
	struct meals *add1;
	struct chips *add2;
	struct drinks *add3;
};

struct order barray[25];


int i=0;
int t=0;
int g=0;
int z=0;
int x=0;
int qt=0;
float total=0;
float price;
int q=0;
int re=0;
int ree=0;
int main()
{
	int order;

	do 
	{
		
		printf("Welcome to Tasty Burgers \n");
		printf("Place your order here...\n");
		printf("\t1.Order Meals\n");
		printf("\t2.Order Burgers\n");
		printf("\t3.Order Chips\n");
		printf("\t4.Order Cold Drinks\n");
		printf("\t5. Process Order\n");
		printf("\t6.Cancel\n");
		printf("\t7.Exit\n");
		printf("Select your option:\n");
		scanf("%d",&order);
		 switch(order)
		 {
			
			
				case 1:
				{
					char n;
					int qty;
					int m;
					while(1)
					{
					    printf("Select the burger type:\n");
					   	printf("A-Big Chicken Meal -20$\n");
						printf("B-Big Ham Meal -22$\n");
						printf("C-Big Vegie Meal -18$\n");
						printf("X-To return to main menu\n");
						printf("Select the burger type:\n");
						fflush(stdin);
						scanf("%c",&n); 
						if(n=='A'){
							if(re==0){
								printf("You have selected Chicken Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=malloc(sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Chicken;
								barray[i].add1->p1->quantity=1;
								
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=20*qty;
								qt=qt+qty;
								printf("Your current bill value $%.2f \n",total);
								re++;
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}else{
								printf("You have selected Ham Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=malloc(sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Chicken;
								barray[i].add1->p1->quantity=1;
								
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=total+20*qty;
								qt=qt+qty;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}
						}else if(n=='B')
						{
							if(re==0){
								printf("You have selected Vegie Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=malloc(sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Ham;
								barray[i].add1->p1->quantity=1;
								
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=22*qty;
								qt=qt+qty;
								re++;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}else{
								printf("You have selected Chicken Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=realloc(barray[i].add1->p1,sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Ham;
								barray[i].add1->p1->quantity=1;
								
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=total+22*qty;
								qt=qt+qty;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}				
						}
						else if(n=='C'){
							if(re==0){
								printf("You have selected Chicken Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=malloc(sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Vegie;
								barray[i].add1->p1->quantity=1;
								
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=18*qty;
								qt=qt+qty;
								re++;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}else{
								printf("You have selected Chicken Meal. How many meals you wish you order? \n");
								scanf("%d",&qty);
								barray[i].add1=malloc(sizeof(struct meals));
								barray[i].add1->p1=malloc(sizeof(struct burger));
								barray[i].add1->p1->Burger_type=Vegie;
								barray[i].add1->p1->quantity=1;
								barray[i].add1->p2=malloc(sizeof(struct chips));
								strcpy(barray[i].add1->p2->cdescription,"Yummy chips");
								barray[i].add1->p2->min_weight=30;
								barray[i].add1->p3=malloc(sizeof(struct drinks));
								strcpy(barray[i].add1->p3->ddescription,"Yummy drink");
								barray[i].add1->p3->quantity=250;
								total=total+18*qty;
								qt=qt+qty;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}					
						}	
						
						else if(n=='X'){
							
							main();break;
						}else{
							printf("Wrong option enter again!\n");
						}
						printf("<<Press Any Key to show the main menu>>\n");
					 _getch();
					
					};
					
					
				break;
			
			case 2:{
					  char s;
					  printf("%f",total);
					  fflush(stdin);
					  while(1){
						  char m;
					   printf("Select the burger type:\n");
					   	printf("A-Chicken Burger -15$\n");
						printf("B-Ham Burger -17$\n");
						printf("C-Vegie Burger -13$\n");
						printf("X - To return to main menu\n");
						printf("Select the burger type:\n");
						fflush(stdin);
						scanf("%c",&s);
						if(s=='A'){
							if(ree==0){
								barray[i].add=malloc(sizeof(struct burger));
								printf("You have selected Chicken Burger.");
								barray[i].add->Burger_type=Chicken;
								price=15;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}else{
								barray[i].add=realloc(barray[i].add,sizeof(struct burger));
								printf("You have selected Chicken Burger.");
								barray[i].add->Burger_type=Chicken;
								price=15;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}
						}else if(s=='B'){
							if(ree==0){
								barray[i].add=malloc(sizeof(struct burger));
								printf("You have selected Ham Burger.");
								barray[i].add->Burger_type=Ham;
								price=17;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}
							}else{
								barray[i].add=realloc(barray[i].add,sizeof(struct burger));
								printf("You have selected Ham Burger.");
								barray[i].add->Burger_type=Ham;
								price=17;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}								
							}
						}else if(s=='C'){
							if(ree==0){
								barray[i].add=malloc(sizeof(struct burger));
								printf("You have selected Vegie Burger.");
								barray[i].add->Burger_type=Vegie;
								price=13;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}	
							}else{
								barray[i].add=realloc(barray[i].add,sizeof(struct burger));
								printf("You have selected Vegie Burger.");
								barray[i].add->Burger_type=Vegie;
								price=13;
								ree++;
								printf("How many burgers you wish you order?");
								scanf("%d",&barray[i].add->quantity);
								q=barray[i].add->quantity;
								total=total+price*q;
								qt=qt+q;
								printf("Your current bill value $%.2f \n",total);
								printf("Press \"Y\" to add more meals into your order or Press \"X\" to go back to the previous menu \n");
								fflush(stdin);
								scanf("%c",&m);
								if(m=='Y'){
									continue;
								}if(m=='X'){
									main();
								}							
							}							
						}else if(s=='X'){
							main();break;
						}else{
							printf("Wrong option enter again!\n");
						}
					  }	
					  printf("<<Press Any Key to show the main menu>>\n");
					 _getch();
			};
			break;
					
			case 3:{
				int a;
				if(z==0){
					printf("You have selected Chips. How many chips you wish you order?");
					scanf("%d",&a);
					barray[i].add2=malloc(sizeof(struct chips));
					strcpy(barray[i].add2->cdescription,"Yummy chips");
					barray[i].add2->min_weight=30;
					total=total+5*a;
					qt=qt+a;
					printf("Your current bill value $%.2f \n",total);
					z++;
				}else{
					printf("You have selected Chips. How many chips you wish you order?");
					scanf("%d",&a);
					barray[i].add2=malloc(sizeof(struct chips));
					strcpy(barray[i].add2->cdescription,"Yummy chips");
					barray[i].add2->min_weight=30;
					total=total+5*a;
					qt=qt+a;
					printf("Your current bill value $%.2f \n",total);					
				}
				printf("<<Press Any Key to show the main menu>>\n");
				 _getch();
			};
			break;
			case 4:{
				int a;
				if(t==0){
				
					printf("You have selected Cold Drinks. How many chips you wish you order?");
					scanf("%d",&a);
					barray[i].add3=malloc(sizeof(struct drinks));
					strcpy(barray[i].add3->ddescription,"Yummy chips");
					barray[i].add3->quantity=250;
					total=total+3.50*a;	
					qt=qt+a;
					printf("Your current bill value $%.2f \n",total);
					t++;
				}else{
					printf("You have selected Cold Drinks. How many chips you wish you order?");
					scanf("%d",&a);
					barray[i].add3=realloc(barray[i].add3,sizeof(struct drinks));
					strcpy(barray[i].add3->ddescription,"Yummy chips");
					barray[i].add3->quantity=250;
					total=total+3.50*a;	
					qt=qt+a;
					printf("Your current bill value $%.2f \n",total);					
				}
				printf("<<Press Any Key to show the main menu>>\n");
				_getch();
			}break;
			case 5:{
				int p;
				if(total>100 && qt>5){
					while(1){
						printf("1-DIS -15%");
						printf("2-DIS -10%");
						scanf("%d",&p);
						if(p==1){
							float dis=(total/100)*15;
							float bill=total-dis;
							printf("Your total bill value is %.2f Discount\n",total);
							printf("- %.2f \n",dis);
							printf("Final bill value is %.2f \n",bill);
							barray[i].total_price = bill;
							barray[i].receipt_no=rand()%25+1;
						   printf("Your receipt number is B00%d \n",barray[i].receipt_no);
						   printf("Please go to a register and make the payment by quoting the Receipt Number B00%d \n",barray[i].receipt_no);
						   printf("<<Press Any Key to show the main menu>>\n");
							re=0;
							ree=0;
							qt=0;
							total=0;
							i++;
							break;
						}else if(p==2){
							float dis=(total/100)*10;
							float bill=total-dis;
							printf("Your total bill value is %.2f Discount\n",total);
							printf("- %.2f \n",dis);
							printf("Final bill value is %.2f \n",bill);
							barray[i].total_price = bill;
							barray[i].receipt_no=rand()%25+1;
						   printf("Your receipt number is B00%d \n",barray[i].receipt_no);
						   printf("Please go to a register and make the payment by quoting the Receipt Number B00%d \n",barray[i].receipt_no);
						   printf("<<Press Any Key to show the main menu>>\n");
							re=0;
							ree=0;
							qt=0;
							total=0;
							i++;
							break;							
						}else{
							printf("Wrong input \n");
							continue;
						}
					}
				}else if(total>100){
					float dis=(total/100)*15;
					float bill=total-dis;
					printf("Your total bill value is %.2f Discount\n",total);
					printf("- %.2f \n",dis);
					printf("Final bill value is %.2f \n",bill);
					barray[i].total_price = bill;
				    barray[i].receipt_no=rand()%25+1;
						   printf("Your receipt number is B00%d \n",barray[i].receipt_no);
						   printf("Please go to a register and make the payment by quoting the Receipt Number B00%d \n",barray[i].receipt_no);
						   printf("<<Press Any Key to show the main menu>>\n");
					re=0;
					ree=0;
					qt=0;
					total=0;
					i++;
				}else if(qt>5){
					float dis=(total/100)*10;
					float bill=total-dis;
					printf("Your total bill value is %.2f Discount\n",total);
					printf("- %.2f \n",dis);
					printf("Final bill value is %.2f \n",bill);
					barray[i].total_price = bill;
				    barray[i].receipt_no=rand()%25+1;
						   printf("Your receipt number is B00%d \n",barray[i].receipt_no);
						   printf("Please go to a register and make the payment by quoting the Receipt Number B00%d \n",barray[i].receipt_no);
						   printf("<<Press Any Key to show the main menu>>\n");
					re=0;
					ree=0;
					qt=0;
					total=0;
					i++;	
				}else{
					printf("Final bill value is %.2f \n",total);
					barray[i].total_price = total;
				    barray[i].receipt_no=rand()%25+1;
						   printf("Your receipt number is B00%d \n",barray[i].receipt_no);
						   printf("Please go to a register and make the payment by quoting the Receipt Number B00%d \n",barray[i].receipt_no);
						   printf("<<Press Any Key to show the main menu>>\n");
					re=0;
					ree=0;
					qt=0;
					total=0;
					i++;					
				}
				printf("<<Press Any Key to show the main menu>>\n");
				_getch();
			};
			break;
			case 6:{
					int s,add;
					printf("Please enter your Receipt Number.\nB00");
					scanf("%d",&add);
					for(int y=0;y<i;y++){
						if(add==barray[y].receipt_no)
						{
							g++;
							i--;
							for(int u=y;u<=i;u++){
								barray[u]=barray[u+1];
							}
							
							printf("Your order has been cancelled.Thank you \n");
							break;
						}
					}
					
					if(g==0){
						printf("There is no order \n");
					}
					g=0;
					printf("<<Press Any Key to show the main menu>>\n");
					 _getch();				
			}break;
			case 7: exit(0);
			
			default :printf("Wrong option ! \n");
		 }	
		 }
	}while(order !=7);
	
}
			

		

		
