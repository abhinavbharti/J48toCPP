J48toCPP
--------

mru, 2011-10-10


Create a C++ implementation of a Weka J48 tree.



Usage:

 * Create a J48 Model using Weka
 * save the model to a file
 * invoke J48toCPP

    java -cp dist/J48toCPP.jar:lib/weka.jar J48toCPP weka_j48_model model

will generate something like this in `predict_model.hpp`:


    #ifndef __predict_model_HPP
    #define __predict_model_HPP
    
    // generated by J48toCPP
    
    // i found no way to reconstruct the original variable ordering
    // predict_model::predict ( diff, nr_white )
    #define DO_predict_model() predict_model::predict ( diff, nr_white )
    
    class predict_model {
     public:
      enum decision { BOUNDARY, NOBOUNDARY };
      static inline decision predict ( const double& diff, const double& nr_white ) {
        if (diff <= 0.056274) {
          return NOBOUNDARY;
        } else {
          if (nr_white <= 8983) {
            return NOBOUNDARY;
          } else {
            return BOUNDARY;
          }
        }
    
      }
    };
    #endif // __predict_model_HPP

