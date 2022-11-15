using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Strings_but_faster
{
    internal class Program
    {
        static void Main(string[] args)
        {
            DateTime start = DateTime.Now;
            string test1 = Concatenator('b', 10000);
            DateTime end = DateTime.Now;
            Console.WriteLine(end - start);

            DateTime start2 = DateTime.Now;
            string test2 = ConcatenatorStringBuilder('b', 1000000);
            DateTime end2 = DateTime.Now;
            Console.WriteLine(end2 - start2);

        }

        // old method
        static string Concatenator(char characterToConcatenate, int count)
        {
            string concatedstring = string.Empty;

            for(int i = 0; i < count; i++)
            {
                concatedstring += characterToConcatenate;
            }
            return concatedstring;
        }

        // new method
        static string ConcatenatorStringBuilder(char characterToConcatenate, int count)
        {
            StringBuilder concatedString = new StringBuilder();

            for(int i =0; i < count; i++)
            {
                concatedString.Append(characterToConcatenate);
            }
            return concatedString.ToString();
        }
    }
}
