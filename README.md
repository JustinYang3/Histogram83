# Histogram83
 DataInputStream data = new DataInputStream (System.in);
      final int MAXRANGE = 10;
      final int MINRANGE = 1;
      final int RANGE    = 10;    //declares variables 

      int[] list = new int[MAXRANGE]; //creates array

      for (int i=0; i<list.length; i++) 
      {
         list[i] = 0;
      }

      System.out.println ("Enter list of integers in range 1-100.");
      System.out.println ("Enter an integer not in the range to quit.");

      System.out.print ("Enter Integer: ");
      Scanner scan = new Scanner(System.in);
      int value = scan.nextInt();

      while (value >= MINRANGE && value <= (MAXRANGE*RANGE)) {

         list[(value-1)/RANGE] = list[(value-1)/RANGE] + 1;
         System.out.print ("Enter Integer: ");
         value = scan.nextInt();
      }

      System.out.println("");
      System.out.println ("Histogram:");
      for (int i=0; i<list.length; i++) {

         System.out.print ("   " + (i*RANGE+1) + " - " + (i+1)*RANGE + "\t| ");
         for (int j=0 ; j<list[i] ; j++) //prints a star as long as there are more integers
         {
            System.out.print ("*");
         }
         System.out.println ();
